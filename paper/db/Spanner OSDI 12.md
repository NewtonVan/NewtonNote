#classic #share_nothing #google 
Time Cost: 105 min
# Background
## Scenarios
* Sql semantic can't be replaced in the daily development totally.
* Google's business distributed in a global level range.
* There are lots of hierarchy relationship in google's business.

## Current Defects
* GFS can't meet all the needs from daily development.
	* It can't provide semantic like database.
	* Consistency model of GFS can't handle the overhead of application.


# Requirements
* Implementing important database features on the top of distributed sytem infrastructure, which is distribute data at global scale, multi-version.
* Offering strong consistency(external consistency).
* Available.
* Manageing cross-datacenter replicated data.

# Motivation
## Gap
* For concurrent operation that will cause conflicts, we need to have a role like global "clock" to help us keep the causality.
* We can use replication for available but we need to keep them consensus.
* KV is good for shard and suit in distributed scenarios. And google has success in BigTable. However, we have to fit relationship model with underlying KV storage.


## Inspiration
* Google has a black magic ==True Time API==. TT API can offer us a global clock ([Loop Jump](https://loopjump.com/google_spanner/)). 
	* This global clock can offer us the global order of the event. 
	* However, this "clock" provide us the global time interval instead of global time. In the words of the article, it provides us time with the bounded time uncertainty.
	* We need to use this to develope our own causality.
* 2PC gives a guidance for global transcation across the zones.
* Combine the application and the system will approve the locality, in both direction.
* Replication will make system available and paxos will fix the conflict of consensus problem.


# Design

## Core idea
* Use TT API to offer the global event order and provide us external consistency.
* For global transcations that across the zone, we can use 2PC to retain consistency.
* Choose replication for availablity and use Paxos makes them consensus.
* Underlying storage we adapt Big Table's design.

## Architecture
### Server Organazation
![[Pasted image 20221221194050.png|400]]
In a nutshell, spanner server architechure follows master-slave style design.
* Universe is the spanner deployment.
* Zone is inner organazation of universe. It's quite like BigTable.
	* Zones are the unit of administrative deployment.
	* Spanserver is where data lives and serves to client.
	* Location proxy route the client for which spanserver to interact.
	* Zone master assigns data to spanservers.
* Universe master & Placement driver is singleton.
	* Universe master monitors the status of zones and provide interactive debugging.
	* Placement Driver is responsible for data automative migrate across the zone. PD will communicate with the spanservers to get their information.


### Spanserver software stack
![[../ref/pics/Pasted image 20221221195219.png|450]]
* Each spanserver is responsible for 100-1000 instances of data structure called tablet. Tablet is very similar to BigTable's tablet, it's a bag of mapping 
	* Bigtable tablet `(key: string, TS: i64)->string`.
	* Spanner assigns TS to data. Achieve multi-version.
* Colossus is successor of GFS. 
	* Tablet's state are stored in B-tree-like files and a WAL.
	* In addition to the data, it also record the metadata for state machine and log for Paxos.
* Paxos, like we mentioned in the core idea, used to make consensus.
	* It's critical have a long-lived Paxos leader in Spanner's implementation.
* The current Spanner implementation logs every Paxos write twice.
	* Once in the tablet's log.
	* Once in the Paxos log.
* On the top of leader, there is a lock table used for fix the concurrent conflicts.
* Transaction manager will take care of global transcation that across the Paxos group for us. If the transaction only involves one paxos group, it will be bypassed.

## Directory & Placement
* Directory
	* Bucketing abastraction.
	* Concept of directory: a set of contiguous keys with the common prefix(can be set with the meaning of business).
	* It's the unit of data placement.
	* Actually, in the implementation, spanner will devide the directory into lots of fragments in case of large directory.
* Tablet in Spanner may contain multiple directories.
	* Spanner's tablet is not necessarily a single lexicographically contiguous partition of the row space.
	* It may encapsulate multiple partitions of the row space.
	* It helps to colocate multiple directories that are frequently accesses together.
* A directory's replication properties can be specified by application.

## Data Model
* Schema in spanner is actually a semi-schema. Application can use relationship data model. However, spanner need every row in  sql model has a name to suit KV storage model.
* For the need of business, spanner provide a hierarchy semantic to make data interleaved from different tables.
![[../ref/pics/Pasted image 20221221204958.png|500]]


## External Consistency
### True Time API
Actually it's expensive black magic. It provides us a ==global clock with uncertainty== in distributed env. 
There are mainly three kinds of API
| API          | Returns                          |
| ------------ | -------------------------------- |
| TT.now()     | TTinterval: [earliest, latest]   |
| TT.before(t) | True iff t has definitely not arrived |
| TT.after(t)  |                                  True iff t has definitely passed|

### Leader timed leases
* Spanner paxos use timed leases to make leadership long-lived(10 secs default). 
* And Spanner make its paxos obey the disjointness invariant: for each Paxos group, each Paxos leader's lease interval is disjoint from every other leader's.

### External consistency
There are two constrain on assigning TS to RW transcations help us satisfy external consistency:
* Start: $t_{abs}(e_i^{server})\le s_i$
	* The coordinator leader for a write $T_i$ assigns a commit timestamp $s_i$ no less than the value of TT.now().latest, computed after $e^{server}_i$.
* Commit Wait: $s_i< t_{abs}(e_i^{commit})$
	* The coordinator leader ensures that clients cannot see any data committed by $T_i$ until TT.after($s_i$) is true
Then we can get external consistency: $t_{abs}(e_1^{commit})<t_{abs}(e_2^{start})\rightarrow s_1<s_2$
![[../ref/pics/Pasted image 20221222003242.png|350]]

And for read, we design $t_{safe}$ timestamp. Every replica tracks a value called safe time $t_{safe}$ which is the maximum timestamp at which a replica is up-to-date. A replica can satisfy a read at a timestamp t if t<= $t_{safe}$, $t_{safe}=min(t_{safe}^{Paxos}, t_{safe}^{TM})$.
For a read only transaction, Spanner executes in two phases: assign  a timestamp $s_{read}$ and execute the transactions' reads as snapshot reads at $s_{read}$.

### Details
* RW transactions. 
	* Like Bigtable, writes in a transactions will be buffered at the client until the commit. This leads to reads  in a transactions don't see the effects of the transaction's writes. 
	* Reads within the transactions use Wound-Wait to avoid deadlock.
	* Two Phase Commit: The client chooses a coordinator group and sends a commit message to each participant’s leader with the identity of the coordinator and any buffered writes. Having the client drive two-phase commit avoids sending data twice across wide-area links.
	* All participant leader need to first acquires a write locks
	* The coordinator skips the prepare phase. It chooses a TS for the entire transaction. And the commit TS $s$ must be:
		* greater or equal to all prepare timestamps (to satisfy the constraints discussed in Section 4.1.3).
		* greater than TT.now().latest at the time the coordinator received its commit message.
		* greater than any timestamps the leader has assigned to previous transactions (again, to preserve monotonicity).
	* The coordinator leader then logs a commit record through Paxos.
	* After commit wait, the coordinator sends the commit timestamp to the client and all other participant leaders. Each participant leader logs the transaction’s outcome through Paxos. All participants apply at the same timestamp and then release locks.
* RO transactions
	* If the scope’s values are served by a single Paxos group, then the client issues the read-only transaction to that group’s leader.
		* Define LastTS() to be the timestamp of the last committed write at a Paxos group.
		* If there are no prepared transactions, the assignment sread = LastTS() trivially satisfies external consistency.
	* If the scope’s values are served by multiple Paxos groups, there are several options.
		* Spanner currently implements a simpler choice. 
		* The client avoids a negotiation round, and just has its reads execute at sread = TT.now().latest (which may wait for safe time to advance).

* Schema Changes

# Experiment
## Design Intention


# Todo


# Reference
* [Loop Jump](https://loopjump.com/google_spanner/)
* [Google去中心化分布式系统论文三件套(Percolator、Spanner、F1)读后感](https://owent.net/2019/1902.html)


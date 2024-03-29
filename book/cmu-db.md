# ACID
## Atomicity 
* Semantic: A txn commit or abort. No other state.
* Mechanisms for ensuring atomicity
	* Logging
	* Shadow Paging

## Isolation
* Semantic: Users submit txns, and each txn executes as if it was running **by itself**.
* To achieve concurrency, interleave trx ops.
	* No interleave => Serial schedules
	* With equivalent concept, we can introduce serializable schedules.
	* More flexibility means better parallelism.
* Consider about conflicts.
	* Definition
		* Different txns.
		* Op on same object, at least one op is write.
	* Different conflicts may lead to isolation break.
		* R-W, Unrepeatable read.
		* W-R, Dirty Read (Read uncommitted but rollbacked data).
		* W-W, Lost Update
	* Introduce conflict equivalent
		* 2 non-conflicting op of different trxs can be swap.
* Use graph theory to model this
	* Tx is a point.
	* Conflicts create edge.
	* Conflict serializable iff dependency graph is acyclic.

### Concurrency Control
* Distinguish Locks & Latches
![[ref/Pasted image 20240328183720.png]]
* Lock has 2 types: Shared & Exclusive.
* 2PL: concurrency control protocol
	* No need to know all queries before execute.
	* Stage
		* Growing
			* Each tx requests locks needed from LockManager
			* The lock manager grant/denies lock requests.
		* Shringking
			* Allowed to only release/downgrade locks that it previously acquired.
			* Can't require new locks.
	* 2 Stage graph ![[ref/Pasted image 20240328185300.png]]

2PL on its own is sufficient to guarantee conflict serializability because it generates schedules whose precedence graph is acyclic. (We can prove that by contradictory). But it's subject to cascading aborts.

* 2PL observations
	* May still have dirty reads. => Strong Strict 2PL
	* May lead to deadlocks. => Detection or Prevention
* Strong Strict 2PL
	* Txn only allowed to release after it has ended (commit/abort).
	* Often stronger than needed.
* Deadlocks
	* Detection
		* Checks cycle for wait-for graph.
		* Choose victim to abort/restart.
		* Tradeoff: check frequency & how long tx wait before deadlocks are broken.
	* Prevention
		* Older = Higher Priority
		* Wait-Die (Old waits for young)
		* Wound-wait (Young waits for old)
* Lock granularities
	* Trade-off: parallelism v.s. overhead
		* Fewer Locks, Larger Granularity vs. More Locks, Smaller granularity.
	* Hierarchical locks are useful in practice because it reduce the lock number. However, it increase the cost to detect locks. Design Intention Locks to hint.
	* Intention Locks
		* Not phsically lock current scope. Hint that lower level in descendent objects.
		* Category: IS, IX, SIX
			* SIX: Shared(physically locked) + Intention-Exclusive
		* New Compatibility Matrix
		* Protocol
			* To get S/IS, must hold at least IS on parent.
			* To get X, IX, or SIX, must hold at least IX on parent.
	* Lock Escalation
		* The DBMS can automatically switch to coarsergrained locks when a txn acquires too many lowlevel locks.
Time Cost: min
# Background
## Scenarios
In memory KV is widely used in many systems. Requirements for this kind of system are efficiency and availability.

## Current Defects
To meet the requirement for fault tolerance, current design adapt Primary-backup Replication. PBR lead to low mem efficiency. And budget is limited.


# Requirements
* High memory efficiency. 
* Available.
* Not significant degradtion with PBR.

# Motivation
## Gap 
Application in large scale require system to provide fault tolerance and available. Simply restore from crash incur non-trivial time. PBR is a common idea to achieve these ability. However, simply copy isn't the best choice for space efficiency.

## Opportunities & Inspiration
* In most scenarios for in memory KV, value usually much bigger than key. This inspire us we can update value seperate with value in storage layer.
* Erasure coding is another good choice to achieve fault tolerance. More importantly, it has better space efficiency than replication.

## Challenges
1. EC is bulk-oriented. But KV metadata and KV pair are scattered.
2. Consistency issue. 
	1. Fault tolerance will involve mutliple machine. 
	2. In the case of EC, it need time to calculate parity blocks. `Set` in a block way isn't a wise choice. 
	3. Concurrent update easily cause inconsistency.

# Design
## Core idea
* Seperate metadata and key from value.
	* Support us to use hybrid pattern for fault tolerance.
* Fix consistency problem with piggybacking style method.


## Architecture
![[../ref/pics/Pasted image 20230412220027.png | 500]]
* The basic unit of EC coding is Coding group.
	* 2 roles: Data Process & Parity Process.
	* Metadata are separated and managed with PBU.
	* Data value implement by EC.
* Update in value will be convert to patch diff.
* Virtual address space for different process will be different to realize fault isolation.
* Update use piggybacking to address consistency problem. 
	* This avoid time consuming 2PC.
	* Strongly consistency use established by an logical clock which monotonously increase.
	* Once the data process received all the resp from parity process, data will be regarded as stabled.
![[../ref/pics/Pasted image 20230412221543.png | 500]]
* Interleaved layout for workload and memory balance.
	* Data process has less metadata than Parity process.


## Recovery
2-Stage
* Preparation: choose recovery process and sync request buffer
* Online recovery: estimated in pic.
![[../ref/pics/Pasted image 20230412222024.png]]


# Experiment
## Design Intention
* Show the improvement in memory space efficiency.
* Approve the system can achieve comparable R/W performance with PBR.
	* Analyze difference on different type of workload.
	* Design experiment to illustrate why the difference happend and prove our theory for explanation.
* Show the system can provide good enough availabity.
	* Here design a blocked version experiment to support our theory that Cocytus need to allocate new block when executing `set` and this will trigger data recovery.



# Todo


# Reference

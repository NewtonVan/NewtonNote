#google #classic
Time cost: 120 min
# Background
## Scenarios
* File System with Large distributed data-intensive applications:
	* Failure on all commodity hardwares are frequent.
	* Files are larger than the traditional standard.
	* Append operation are more frequent than updating in place.
	* Workload mainly contain large streaming access and some random access.
* Rule of thumb:
	* Co-designing applications and FS API will gain flexibility.

## Current Defects
Previous distributed system has a marked departure from the application scenarios(application workload & tech env).

# Requirements
* Scalable distributed FS for large scale data-intensive workload.
* Fault tolerance.
* High aggregate performance.
* Suit for high performance concurrent write(mostly are append).
* High sustained bandwidth is more important than low latency.
* Similar FS interface for flexibility.


# Motivation
## Gap
* File size are larger than the standard big file.
* Distributed system are deployed on inexpensive commodity hardwares with high probability to fail.
* Workload contain large streaming access.


## Inspiration
* Use replication to meet the fault tolerance and availability.
* Single master architechure help us to manage core information for us.
* Release the traffic on master, don't make it to be bottleneck.


# Design

## Core idea
* Single master architecture with replication. Core information are managed by master.
* Use replication to achieve availablity and fault tolerance.
* Distinguish the data flow.
* Offload the burden of master to avoid it becomes the bottleneck.
* Design consistency model.

## Architecture
![[Pasted image 20221219170531.png]]
* Master
	* Communicate with client for core information
* Chunkserver
	* Each chunk is identified by ==uniq, global, immutable== id.
	* Large chunk size is very important.
		* Reduce the burden for master managing metadata.
		* Reduce the interaction with client.
		* More likely to perform many operations on a given chunk, reduce the network overhead.
	* linux FS.
	* replicated.

==**System interactions**==
![[Pasted image 20221219171550.png]]
* Minimize the involvment of master.
* Depart the data flow
	* topology: data transferred in a chain style
	* Find the closet machine.
	* Pipelining the data transfer.
* Atomic append
	* For multi concurrent writer.
	* Need to check out of size.
	* Details check the [blog](https://spongecaptain.cool/post/paper/googlefilesystem/#35-consistency-model-%E4%B8%80%E8%87%B4%E6%80%A7%E6%A8%A1%E5%9E%8B).
* Snapshot

## Master & metadata
### Metadata:
* Persistent
	* Namespace
	* Mapping file name to chunk 
* Maintained by heartbeat
	* Location

These meta data are stored by in-mem data structure. Benifits are:
* Good for performance.
* Backgournd scan.

Operation log contains the history of the critical metadata changes. And it's central to GFS.
* The only persistent record of metadata.
* Serves as a logical time line.
For faster recovering(replaying the persistent log), log has to be small.

### Master operaition
* Namespace management and locking
	* unlike traditional FS, namespace in GFS logically are lookup table mapping pathnames to metadata.
	* Locks contains two type.
		* Write serialize attempts to create file with the same name.
		* Read lock on the directory name suffices to prevent the directory from being modified.
* Replica placement
	* Challenge is ==multi-level distribution==.
	* Two purpose:
		* Maximize reliability & availability.
		* Maximize bandwith utilization.
* Creation, re-replication, rebalancing. 
	* Creation
		* Equalize resource utilization
		* Limit the number of "recent" creation on each chunkserver.
		* Spread replicas of a chunk across rack.
	* Re-replication
		* How far to re-replicate goal.
		* Liveness.
		* Minimize the impact of failure.
	* Rebalancing is regularly. Combined with scan and etc.
* GC.
* Stale replica detection.(Chunk ver number)

## Consistency model
It's a relaxed consistency model.
* GFS
| State              | Write                    |             Record Append              |
| ------------------ | ------------------------ |:--------------------------------------:|
| Serial success     | defined                  | defined interspersed with inconsistent |
| Concurrent success | consistent but undefined | defined interspersed with inconsistent |
| Failure            | inconsistent             |              inconsistent              |

* Application
	* mainly append.


## Fault tolerance
* High availability
	* Fast recovery
	* Replicate master
	* Replicate chunk
	* Diagnose tools
* Data Integrity: checksum
* Diagnostic tools

# Experiment
## Design Intention


# Todo


# Reference
* [notes](https://spongecaptain.cool/post/paper/googlefilesystem/#35-consistency-model-%E4%B8%80%E8%87%B4%E6%80%A7%E6%A8%A1%E5%9E%8B)
* [解读Google分布式文件系统GFS（合集）_哔哩哔哩_bilibili](https://www.bilibili.com/video/BV1fT411c7y6/?spm_id_from=333.999.0.0&vd_source=7781261991941d597260a7d004b83d25)
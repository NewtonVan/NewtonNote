Time Cost: 180 min
# Background
## Scenarios
* Cloud-native database meet increasing demand on scaling compute resources and memory resources **Elastically** & **Independently** 
* SOTA cloud-native DB still embrace monolithic architecture.
	* Tightly couple compute & memory resource.
	* Spare resource scattered across the cluster which is hard to fully utilize.


## Current Defects
* Heavy crash recovery for RDMA-based DB
	* Not fully utilized independency between local buffer pool & remote buffer pool
* Current RDMA-based DB's management highly depends on underlying    kernel.
	* Incur notable degradation
	* Ignore unique data access pattern in DB scenario

# Requirements
* Cost-effective and elastic clout-native DB
* Fast failure recovery
* Comparable performance with monolithic DB


# Motivation
## Gap & Challenges
Cloud-native app persue elasticity and cost-effective. Based on RDMA, LegoOS has provide a provision on how to design disaggregation system. Similar idea can be transferred into database.

However, current design for database have lots of shortcoming for build RDMA-based disaggregation archetecture.
1. The cost of crash recovery and scaling is heavy.
2. Their memory management managed by underlying kernel, which produce notable degradation.


## Opportunities & Inspiration
* RDMA provide opportunity for pooling memory resource.
	* In the ideal situation, appliation can access infinite memory resource.
* Push down mermory management to DB
	* Bypass kernel IO stack
* After disaggregate memory pool, the crash recovery can also be split into multi-stage to avoid "long history" to recovery.


# Design

## Core idea
* Separate memory resource and Pooling remote memory.
* Co-design database kernel with disaggregation.
* Split ARIES protocol to independently handle the local and remote memory failures.
	* 2-tier ARIES
	* cNode treat remote buffer as a persistence layer
	* offload the duty of ensuring data persistence to the remote memory


## Architecture
![[../ref/pics/Pasted image 20230407225435.png | 500]]
* Whole system is divided into 3 components
	* Compute node(cNode)
	* Global Memory Cluster(gmCluster)
		* allocate infinite remote memory
	* Persistent shared storage(pStorage)
		* availability
		* crash consistency
* cNode exec SQL by interacting with Local Buffer Manager
* Multi-phase ARIES protocol are assigned to cNode and RBP
* cNode & gmCluster
	* Remote Buffer Agent serve as proxy of gmCluster. Manage necessary metadatas and execute fast remote R/W
	* cNode persist WAL to pStorage as usual
	* push checkpoints & dirty pages to **gmCluster** at high frequency
* gmCluster
	* offload the original checkpointing and dirty page flushing logics from cNode to the Heavy Fault Tolerance Daemon residing on the memory node of gmCluster

## Database-Aware memory disaggregation
### Local And Remote Memory Management
![[../ref/pics/Pasted image 20230410074013.png]]
* 2 LRU list
	* LRU_LBP reside in both local and remote
	* LRU_LBP is Remote only. Its pages are evicted
* PHASH_LBP provide hash index for metadata in LRU list
* Additionally, LRU_RBP enables cNode access Remote with fast RDMA op

### Memory Page Access
* Memory page access mainly consider 2 path: R&W. And read is more basic, because most write have to read firstly.
* Always remember, SQL engine exec query by interacting with Local Buffer Manager
* Read concern about cache mechanism
	* Cache hit LRU_LBP, access local.
	* Cache hit LRU_RBP, fast one-sided RDMA op, LRU_RBP -> LRU_LBP(**not copy**)
	* Missed
		* read from pStorage first
		* update PHASH_LBP
		* Flush into remote
		* update LRU_LBP
* Wpath are quite similar with read path, difference involves fault tolerance mechanism.

### Page Eviction and LRU
LRU act differently in LRU_LBP & LRU_RBP.
* LRU_LBP follows the LRU design in MYSQL
	* mid-point insertion strategy
	* Access make a page young, move it to the top of queue
* LRU_RBP
	* no mid-point insertion, since no new page will be inserted here

Eviction will be different accordingly.
* LRU_LBP, remove it in LRU_LBP and add it to LRU_RBP
	* Unmodified, simply update metadata
	* Dirty, flushing, tell local page allocator, then move metadata
* LRU_RBP
	* Unmodified, Deregister & clear metadata(PHASH_RBP, PHASH_LBP and etc)
	* Dirty, flush then clear metadata

Dirty Page flushing are time-consuming, use BG task triggered by resource & inbalance detecting


### Efficient RDMA
One sided RDMA need well notification design. Mainly 2 techniques are involved here: Polling and Event Driven
* Polling negligible overhead and high CPU
	* latency sensitived: register, R/W
* Event driven is time consuming but little CPU resources needed
	* BG Evict

LegoBase use a fix sized pages

## Fault tolerance and State Recovery
### 2 tier ARIES
![[../ref/pics/Pasted image 20230410082839.png]]


### Consisten & Fast Flush
* Partial write meet crash, add a connection buffer for notification to gmCluster. Then gmCluster will be confidence that the page flushing has been completed.
* Futher more, make gmCluster actively pull by RDMA read.
* Write locks may be blocked by Background flushing. This produce connection(limit & precious) wasted. Extra copy to save the content in the connection buffer. Release the connection immediately.

### Recovery
Consider 2 case
* cNode crash: cNode read latest tier-1 checkpoint
* Both cNode and gmCluster: cNode read tier-2 checkpoint, cache miss handling will help recover gmCluster
	* Long cold start, to address this, add backup remote when budget permits(**In my opinion, not practicable for industry**)



# Experiment
## Design Intention
* Performane measurement aims at comparable result with monolithic MYSQL. 
* Except regular performance measurement, we should on feature of LegoBase, i.e. elasticy, cost-effective, and State recovery.
* What's more, we should design proper experiment to explain the benefits for remote buffer. 
	* In this work, we achieve this goal by adjusting the size of local memory size.
	* In my opinion, the order of presentation of this part isn't quite proper.


# Todo


# Reference

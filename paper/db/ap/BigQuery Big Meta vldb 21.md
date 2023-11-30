Time Cost: min
# Background
## Scenarios
* ap
* Meta data is big
* Big query
	* Dremel as query engine.
	* High available distributed file system.
	* Physical plan is dynamic. Affected by runtime statistic.
![](../../ref/pics/Pasted%20image%2020231129231722.png)
* 2 kinds of metadata management.
	* Smaller parts in centralized service. Verbose metadata at the block level(HIve).
	* Store a small amount of summarized metadata in the centralized state(Redshift).

## Current Defects
* When meta data is big, scalability is a severe issue.
* Defects in metadata management
	* Hive-like. The cost to opening the block is equivalent to scanning some columns in it.
	* RedShift-like. Centralize will limit the scalability.

# Requirements
* Real time ingestion and ap query runtime.
* Meta data is scalable.
* Support ACID.


# Motivation
## Gap 
* TP require efficiency in index. AP scan the entire block, require scan optimizing techniques.
* AP can use min/max to filter unused block. However, the cost to fetch min/max metadata is the same as scan the block.

## Opportunities & Inspiration
* We can store some useful metadata about physical information for each block into metadata.


## Challenges
* Centralized metadata will limit the scalability of the amount of metadata.
* As table sizes grow, trade off between scale and performance.


# Design
## Core idea
* Design an inner system table(CMETA) to manage the metadata of user table.
	* Design to contain some useful statistic meta information in CMETA.
* Use columnar storage to store these metadata

## Metadata management
* Metadata can be divided into 2 parts.
	* Logical: visible to the user, schema info, partitioning and clustering info.
	* Physical: map table name to actual data.
* Example
1. User table
![](../../ref/pics/Pasted%20image%2020231130114744.png)
2. Corresponding  CMETA
![](../../ref/pics/Pasted%20image%2020231130114832.png)
![](../../ref/pics/Pasted%20image%2020231130114841.png)

3. Columnar Metadata design rules.
![](../../ref/pics/Pasted%20image%2020231130114933.png)

### Incremental generation
* Modification is at block granularity.
	* modification will delete old and create new block.
* Perform LSM style merges on the change log.


# Experiment
## Design Intention


# Todo


# Reference

Time Cost: min
# Background
## Scenarios
* Increasing and diverse demands and exploding data volume.
* Using lots of existing google infrastructure.

## Current Defects
* Expensive to maintain specific infrastructure and ETL cost.
* Each system use different language api.

# Requirements
* Meet diverse demands.
	* ad-hoc
	* dashboard
	* embedded statistics
* Data needs to loaded into multiple system. 
	* ETL leading to additional resource consumption.
 * Underlying components have performance, scalability and efficiency issues.

# Motivation
## Gap 
* Restrictions on underlying infrastructure components.
	* Colossus
		* Common metadata operation involves RPC. Significantly time-consuming than local storage.
		* Data is immutable.
		* Durable data can only be accessed from remote. Increase tail latency and higher cost.
	* Shared-compute
		* Vertical scaling is challenge. Different task has different resource demands.
		* Borg master can often bring down machines for maintenance, upgrades, etc.
* Involved different type data source. Batch data & Realtime data.

## Opportunities & Inspiration
* Colossus
	* Since durable data file is immutable, cache will be simple to manage.
* Shared compute
	* Prefer many small tasks rather than a small number of tasks.

## Challenges
* Data source is mixed. Batch & Real time.
* Underlying 


# Design
## Core idea
* Optimize query engine with lots of tech.
* Design Artus, which fully considered for Procella.
* Cache data and improve memory structure efficiency.

## Architecture
![[../../ref/pics/Pasted image 20231203011126.png]]

### Data
* Using light weight secondary structures.(zone map, bloom filters)
* Data ingestion
	* Batch. Avoid scanning. Lazily generate expensive secondary structures. 
	* Realtime. Data stored in DS's memory buffer, regularly checkpointed to Colossus. Having the data follow two parallel paths allows it to be available to queries in a dirty-read fashion in seconds or even sub-second, while being eventually consistent with slower durable ingestion.
	* Integrating loading into the query engine reduces scalability and flexibility for teams who want to import large (often petabytes) of existing data quickly into Procella. The tool takes the input and output schemas and data mapping, and executes an offline MapReduce based pipeline to create data in Procella optimized format and layout

## Optimizations
* Caching
	* Colossus metadata caching.
	* Header caching.
	* Data Caching.
	* Metadata caching.
	* Affinity scheduling. 
> The caching schemes are designed such that when there is sufficient memory, Procella essentially becomes a fully in-memory database. In practice, for our reporting instance, only about 2% of the data can fit in memory, but access patterns and cache affinity ensures that we get 99%+ file handle cache hit rate and ˜90% data cache hit rate.

* Data format
	* Custom encoding instead of generic algorithm. 
		* This ensures that it can seek to single rows efficiently without needing to decompress blocks of data, making it more suitable for small point lookups and range scans. 
		* Each encoding has estimation methods for how small and fast it will be on the data supplied.
		* Chooses encodings that allow binary search for sorted columns.
	* Uses a novel representation for nested and repeated data types.
	* Directly exposes encoding information to the evaluation engine.
	* Records rich metadata in the file and column header. (Actually, this metadata is aimed at promoting prune efficiency)
	* Supports storing inverted indexes.
* Evaluation engine
	* Procella needs to serve both analytical and high QPS serving use cases.
	* Procella evaluation engine, Superluminal
		* Makes extensive use of C++ template metaprogramming for compile time code generation.
		* Processes data in blocks to take advantage of vectorized computation and cache-aware algorithms.
		* Dynamically combines filters and pushes them down the execution plan
* Partitioning and Index
* Distributed operations
	* Distributed joins
	* Addressing Tail Latency
		* Maintain quantile.
		* Limits the rate and batches.
		* Priority high for smaller queries and low for larger queries.
	* Intermediate Merging
		* Final will be single node. Become bottleneck.
* Query Optimization
	* Virtual Tables
	* Adaptive tech(join/agg/sorting). It has limitation on small queries.


## Recovery

# Experiment
* Some pic is not clear and ambiguous.

## Design Intention


# Todo


# Reference
* [Procella@Youtube 把计算加速玩到极致的实时计算引擎 | 马云雷的技术博客 (mayunlei.github.io)](https://mayunlei.github.io/2020/05/20/Procella-Youtube-%E6%8A%8A%E8%AE%A1%E7%AE%97%E5%8A%A0%E9%80%9F%E7%8E%A9%E5%88%B0%E6%9E%81%E8%87%B4%E7%9A%84%E5%AE%9E%E6%97%B6%E8%AE%A1%E7%AE%97%E5%BC%95%E6%93%8E/)
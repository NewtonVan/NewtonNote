#msra #classic #share_everything 
Microsoft's process for doing research is really well thought out

# Background
## Scenarios
- More and more institutions prefer using cloud db
  - 'pay as you go'  style
  - The main reasons to move into the cloud are security, time-to-market
- Current cloud db service not very scalable
  - HADR
    - On the negative side, the size of a database cannot grow beyond the storage capacity of a single machine
    - O(size-of-data) operations also create issues
  - Spanner
    - automatically shards data logically into partitions called splits
  - Aurora
    - Shared disk
    - Storage tier
## Current defects
- O(size of data) operation time complexity limits the size of the database
- The size of db cannot grow beyond the storage capacity of a single machine

# Target
- Higher security, higher availability, lower and more flexible cost with high performance
- database-as-a-service” to be highly available, support large databases, highly performant, elastic and grow and shrink with the workload 
# Motivation
## Gap
- Meeting all these requirements on the target is not possible in the cloud using the traditional monolithic database architecture
## Inspiration
### SQL server feature:
- Page version store
- Accelerated Database Recovery
  - Unbounded undo phase
- Resilient Buffer pool extension
  - Buffer pool extension (BPE) which spills the content of the  in-memory database buffer pool to a local SSD file 
  - extended this concept and made the buffer pool resilient; i.e., recoverable after a failure
  - serves as the caching mechanism for pages both in the compute and the storage tiers 
- RBIO protocol
  - Stateless and strong typed
  - Automatic versioning
- Snapshot Backup/Restore
  - Log structured: backup in constant-time (it merely needs to keep a pointer (timestamp) to the current head of the log)
- IO stack virtualization

### Design goal and principles
- Separation of the storage and the compute.
- Trade-off between Local, Fast  storage and Cheap, Scalable, Durable  Storage
  - layered, scale-out
  - avoids fragmentation and expensive data movement
- Bounded time operation
  - management of the database log (staging), tiered caching with asynchronous seeding of replicas
- From shared-noting tho shared-disk
- LowLog Latency, Separation o fLog
- Pushdown Storage Functions
- Reuse the components, Tuning, Optimization


# Design
## Core idea
- Separation of the storage and the compute.
- Log is first citizen
- opportunities to move functionality into the storage tier,
- tiered and scaled-out storage
- bounded operations

## Architecture
![[Pasted image 20221207171020.png]]

- XLOG & XSTORE is the "truth" of the database
- Decouple the log function from the local server into a service
- Disseminate the functionality into different layers
  - The top layer is computer node
    - RBPEX: in-memory and SSD
    - Only primary node can update the log
    - Secondary node can read
  - Next layer is XLOG
  - Third layer is page servers: storage tier
    - They serve pages to compute nodes
    - checkpoint data pages and create backups
    - Like Compute nodes, Page Servers keep all their data in main memory or locally attached SSDs for fast access
  - The bottom layer is XSTORE
    - XSTORE are also responsible for recovery

## XLOG service
### Landing Zone
![[Pasted image 20221207171036.png]]

The Primary Compute node writes log blocks directly to a landing zone (LZ) which is a fast and durable storage service that provides strong guarantees on data integrity, resilience and consistency
- Fast, possible expensive, small

### Feature
- Allows concurrent log reader to read consistent information in the presence of log writer without synchronization
- There is XLOG process asynchronously disseminates the data to page servers and secondaries
  - Write synchronously & reliably LZ for durablity
  - Write asynchronously to xlog process for availability
  - XLOG process only writes the hardened logs(loading into pending zone after hardened)
- To disseminate & archive log blocks, design a storage hierarchy
- LogBroker doesn't track consumers, it only maintains a main memory hashmap(seq map), which records the log blocks at the top level.
- Stateless nature

## Primary Compute Node & GetPage
Snapshot isolation

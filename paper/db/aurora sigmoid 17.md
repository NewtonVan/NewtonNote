#aws #share_everything

# Background
- Category
  - Industry design
- Problem to solve 
  - Large scale oltp engine
  - Network become bottleneck
  - 

# Design
## Durability at scale
- Replication, design point of tolerating
- Segmented storage
  - Minimize mttr
  - Partitioning small fixed size segments
  - Segments unit of independent background noise failure and repai
## Offload workload to storage service
- db is log 
- The process of crash recovery is spread across all normal foreground processing. 

## Recovery
- Partitioning small

## Log march forward
- Asynchronous processing
  - VDL 
- Quick recovery

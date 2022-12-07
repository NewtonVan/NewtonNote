#classic #ali #share_everything 
# Background
---
Abstract Alibaba runs the largest e-commerce platform in the world serving more than 600 million customers, with a GMV (gross merchandise value) exceeding USD 768 billion in FY2018.
- Feature of our problem
  - drastic increase of transactions per second with the kickoff of major sales and promotion events
  - a large number of hot records that can easily overwhelm system buffers
  - quick shift of the "temperature"
- Requirements: how efficiently data can be made durable and retrieved from the storage.

## Key Challenge
---
- Tsunami problem
- Flood Discharge
- Fast moving current

## Contribution
---
![[Pasted image 20221207171454.png]]

## Motivation
---
- Using the different latency between different storage, mitigate in an asynchronous way
  - Multi-staged pipeline
  - Asynchronous writes
  - Asynchronous IO in compaction which is decomposed into 3 phases
- Reduce CPU & IO
  - Data reuse
  - FPGA offloading

# Design
---
## Overview
---
- Storage layout
- Read Path
- Write Path
- Flush and compaction

## Storage Layout
---
- Hierarchical storage layout divided by temperature
- Active mem table -> immutable mem table -> tier storage

## Read Path
---
- Design extent
  - With block index for reuse during compactions
- Incremental cache placement
  - Compaction may invalidate the irrelevant cache
  - Replace the old blocks with the newly merged at the same place
- Introduce metadata to manage data files
- Use locality
  - Point lookups are the majority
  - Row cache, temporal locality: even the record in the largest layer, can be cached and accelerate the query
  - Spatial locality, table and block cache
- Multi version metadata index
  - In a COW manner

## Write Path
---
- Decouple writes from the transaction
  - Group them for batch processing
  - Distribute write task into lock free queue
- Multi-stage write to build pipeline. Core idea is mitigate the in-mem operation into IO. And we can achieve this according to the different latencies between disk and memory.
  - Log flush
  - Write mem-tables
  - Commit
- 

## Flush and compaction
---
- Original algorithm
  - Consume significant CPU & DISK IO
  - Write amplification
  - Invalidate cache even if values stay the same
- Accelerating compaction using data reuse (for extent)and data copy (for data blocks)
  - Extent futher divided into data blocks
- FPGA offloading CPU

#share_everything #ali
# Background
---
- DBMS migrate to the cloud
  - Long for
    - Better availablity
    - Elasticity
    - Lower costs
  - Disaggregated DC is the trend

## Contribution
---
- Polardb serverless
  - On demand provisioning
- Optimistic lock
- Index aware prefetching

## Motivation 
---
- Three types architechture
  - Monolithic engine
  - Virtual machine with remote disk
  - Shared storage
- These architecture have a similar problem: resource tightly coupled.
- Separation of calculation and storage improves the utilization of storage
  - Memory resources remain lacking flexible and scalable
- Memory pools are proposed to decouple the resource further
  - Local memory are remained
  - Multi-tenant
- Performance
  - Heavier network
  - Optimistic locking
  - Index-aware prefetching

# Design
---
## Overview
---
- Design remote memory pools
  - Faster than remote storage
  - Improve memory utilization
- New issues to address
  - Remote memory slower than local memory?
    - Tiering memory system
    - Optimization like prefetch
  - Mutual exclusion? Global Latches?
    - One side RDMA
    - CAS
    - Optimistic Locking
  - Network Burden
    - log is db 

## Disaggregate memory
---
- Design 5 api
  - Slab is allocation unit
- Remote memory management
  - Nodes serve slab are slab nodes
  - Home node contains instance-wise metadata
  - Page materialization off loading
- Local cache
  - Reduce network burden
- Cache coherency

## Concurrency Control for B+ tree
---


## Snapshot isolation
---

## Page materialization offloading
---

## Auto scaling
---

# Optimization & Recovery
---
- Index-aware prefetching
- Optimistic locking
- Recovery level
  - Database node
  - Memory node
    - Unplanned
    - Planned
  - Cluster recovery

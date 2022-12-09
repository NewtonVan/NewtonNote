#share_nothing #classic 
Time cost: 75min
# Background
---
- The emergence of the cloud provision the possibility for elasticity.
- Traditional relational db hold back the progress in this direction
- Relationship of data has also changed
- Hadoop still keeps the traditional relationship model, to improve performance takes the complexity of engineering at cost.

# Target 
---
- Improve the elastic of the database
- Better performance/price

# Motivation
---
Why are we blocked?
Pure shared noting tightly couples compute and storage:
- Heterogeneous Workload
- Membership changes
- Online upgrade

# Design
---
## Architecture
---
- Data Storage
  - Shared
  - Immutable table files
  - S3
- Virtual Warehouse
  - Elasticity and Isolation
  - Local cache & File stealing
  - Execution engine
    - Columnar storage
    - Vectorized
    - Push based
- Cloud service
  - Query management and Optimization
    - Cost based
    - Postponing decision until exectuion
    - Concurrency control: snapshot isolation -> MVCC
  - Prunning
    - Instead of building indices, using min-max based pruning to avoid random access

## Feature
---
- Pure saas
- Continuous availability
  - Resilience
  - Online upgrade
- Semi-structured and schema-less data
- Security
- Decouple storage and computation

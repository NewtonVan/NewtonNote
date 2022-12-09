#share_nothing #classic 
# Background
---
- Challenge
  - Global OLTP workload
  - High available
  - Strong Consistency
- Requirement
  - User data close to where use accessing data frequently
  - Fault tolerant
  - To avoid data anomalies and to simplify application development, the DBMS must support SQL with serializable transactions.
## Motivation
- Raft made alived
- Snapshot isolation removal
- Scalabel sql layer
# Contribution
---
- Geo distributed partitioning & replica placement
- Novel transacation
- Fault tolerant & High availablity

# Design
---
## Overview
---
![[Pasted image 20221209162158.png]]

## Transactions
---
- To meet high performance requirements, introduce parallel commits and write pipeline
- Key idea: To improve performance that requires serializable, aysncronous is the common idea. What's more, we can use pipeline to depart some behaviour that woudn't cause conflict in the transaction, i.e., decompose the total transaction into multi-stage
- Wirte pipeling
  - Write stage & commit stage
  - Irrelevant keys wont' cause conflict, so use asynchronous write instead of waiting for all the replicas.
- Parallel commit
  - Recording the state of transaction

## Concurrency control & atomicity
---
- Write intent(use a pointer to get) and transaction state record
- 
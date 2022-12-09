#classic #google #share_nothing 
# Background
---
- Large scale access
- Require Scalability & Reliability 
- Spanner
  - Scalable
  - High Availabity

## Goal
---
- NoSQL
  - High Availability
  - High Scalability
- Traditional RDBMS
  - Consistency like traditional database
  - Usbility

# Motivation
---
- Separation of storage and process
- F1 servers are stateless and hold no data, providing the scalability
- New spanners to satisfy the storage on demand. This is transparent for F1 server

# Design
---
## Architecture
---
![[Pasted image 20221209162427.png]]
- Interact through client. Client connects to F1 server
- Slave Pool process distributed query plan, which are usually quite complex
- F1 master maintains Slave Pool

## Spanner
---
- KV store
- Time stamp for consistency

## Hierarchical Schema
---
- Reduce shuffle
- Benefit join

## Index
---
- Local: contain primary key
- Global: need more participant -> require 2pc, long write are not suggested

## Online Schema Change
---
Challenges
- Different dc location
- In mem state
- Queries and transactions must continue
- Sys availability and latency can't negatively impacted

Solution
- Insert multiple phases to smooth the change
- At most 2 schema co-exist & grant lease 

## Transaction
---
- Snapshot 
- Pessimistic 
  - Deliver the duty to spanner. it must get lock, and client has to connect to the special f1 server 
- Optimistic (default)

## Change History
---
- Change batch pb
- Subscribe-publish

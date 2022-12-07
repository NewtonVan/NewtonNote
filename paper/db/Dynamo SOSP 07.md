#classic #aws #share_everything 
# Background
---
- Problem to solve
  - Reliability at massive scale
  - Highly scalable
  - Customized tradeoff among available, consistency
- Amz Feature
  - Decentrailized
  - Loosely coupled
  - Service oriented
- Common pattern
  - Ineffciencies
  - Limit scale
  - Limit availability
- Scenarios feature
  - Not required complex querying
  - Not required management functionality offered by RDBMS
  - Store and retrieve by primary key
- Sys assumptions & requirements
  - Query model
    - Simple read & write, identified by a key
  - Acid: 
    - Weaker consistency
    - Not provide any isolation guarantees
- SLA
- Design consideration
  - When resolves conflicts: push the complexity to the reads
  - Who : last write wins
  - Other principle
    - Scale out
    - No distinguished node
    - Decentrailization
    - heterogeneity

# Motivation & Idea
---
- Sacrifice consistency under certain failure scenarios
  - Eventually consistent storage
- Consistent Hash
  - Virtual node
- Gossip-based distributed failure detection & membership protocoll
- Quorum reconciliation mechanism
- Object versioning

# Design
---
## Overview
---
![[Pasted image 20221207170030.png]]

## Interface
---
Context: metadata object

## Partitioning
---
- Consistent hash
- Virtual nodes
  - Node unavailable, evenly disperseed
  - Available again, roughly equivalent

## Replication
---
- Replicated with N hosts, N is the so-called "per-instance" parameter
- To address the impact of vitrual node( we want more physic nodes to store the specific key), skipping positions were introduced.
- Nodes for articular key: preference list

## Data versioning
---
- Why do we need it?
  - Asynchronously propagate updates to the node
- Vector clock
  - Target: causality capturing
  - (node id, counter)
  - Size grow?
    - Not likely, handled by one of the top N nodes in the preference list
    - Not handled by top N preference list? Truncation scheme
- Still conflict, vector clock doesn't help
  - Reconciliation when read

## Temporary failure
---
- What happened while get() and put()
  - Router: generic load balancer
  - Coordinator: node handling W & R
  - Consistency protocol: quorum systems, (N, R, W)
  - put() generate a new version
- Hinted handoff
  - problem: Traditional quorum problem: unavailable during server failures & network partitions, reduces durability
  - Solution: "sloppy quorum"
- Object is configured that spread across multiple dc

## Permanent Failures
---
- anti-entropy protocol
- Detect fast? Merkle tree were introduced
  - hash tree, 
  - leaf nodes hash of the values that belong to individual key
  - Higher node: hash of respective children
  - Pros: checked independently, reducing the amount of data that needs to be transferred(minimize the cost of communication for check)

## Membership & failure detection
---
- A gossip-based protocol propagates membership changes & maintains an eventually consistent view of membership
- To prevent logically partitioned ring, propose the roles called seed
  - Known to all nodes
  - External mechanism

# expreiences
---
- Business logic specific reconciliation
- Timestamp based reconciliation
- High performance read engine
- Consistency protocol (N, W, R)
  - N durability
  - W, R availability, durability & consistency
- Balancing performance and durability
- Ensuring uniform load distribution
- Divergent versions: when and how many
- Client driven coordination
  - Why not server-driven coordination
The latency improvement is because the clientdriven approach eliminates the overhead of the load balancer and the extra network hop that may be incurred when a request is assigned to a random node.
- Balancing background vs. foreground tasks
  - Resources are shared across all bg
  - This sharing will affect the performance of normal operation
  - Fg monitor and control
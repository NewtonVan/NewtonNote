# Background
---
- Great success of the practice of dynamodb

# Highlight
---
- Consistent performance at scale
- Serverless experience
- Fundamental properties
  - Frees developers
  - High utilization of resources
  - Elastically
  - Predictable performance
  - Highly available
  - Flexible
- Experience
  - Adapting, partitioning scheme
  - Continuous verification
  - Maintaining high availability as sys evolves
  - Designing systems for predictability over absolute efficiency improves system stability

# Architecture
---
- Leader replica
  - Paxos
  - Leader read
  - Strongly consistent read
  - WAL
- Extra log replicas
- Metadata service
- autoadmin

# Provisioned to on-demand
---
![[Pasted image 20221207170357.png]]

# Durability and correctness
---
## Hardware failures
---
- Log replica(only log, no b-tree)
- Less time healing storage replica

## Silent data err
---
- Checksum

## Continuous verification
---
- Providing conidence

## Software bugs
---
TLA+

# Availability
---

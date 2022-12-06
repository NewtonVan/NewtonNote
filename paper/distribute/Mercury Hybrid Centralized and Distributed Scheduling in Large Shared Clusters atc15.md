#msra
Tasks, which are more important and take more time, will be applied in a centralized way. To fully utilize the idle resource, using distributed schedules for shorter tasks.

# Background
## Scenarios
- "Big Data" Computing
- Diversity of applications sharing a single cluster growing dramatically

## Current defects
- Distributed scheduler 
  - require costly consensus building among schedulers to enforce strict invariants, or relax our guarantees, thus forfeiting R2
- "executor" model had been advised
  - Reusing containers is the key
  - Require similar characteristics among the tasks which will reuse the container
  - Since the same system-level process is shared across tasks, the executor model has limited applicability to within a single application type.
- Centralized scheduler 
  - Bigger the scale of tasks grows, the heavier the schedule cost(eg. heartbeats)
  - Critical path of all allocation decisions poses scalability and latency concerns. . This compromise becomes problematic if typical tasks are short

# Target
There is a summary of requirements in the paper.
- Diverse application frameworks
- Strict enforcement of scheduling invariants
- Maximized cluster utilization and throughput
- Fine grained resource sharing
- Scalability & Efficiency

# Motivation
## Gap
Present as challenges in the paper
- Support diverse application frameworks
- Strict Enforcement scheduling invariant
- Provide high cluster throughput with low-latency allocation decisions

## Inspiration
- Centralized
  - Strict, secure enforcement of scheduling invariants for heterogeneous
- Distributed
  - Scalable, efficient

# Design
## Core idea
- Trade off between the cost of schedule and the cost of execution
Applications may now choose to accept high scheduling costs to obtain strong execution guarantees from the centralized scheduler, or trade strict guarantees for sub-second distributed allocations
- Categorize requests to different type
  - GUARANTEED
    - Highest priority
    - Guaranteed to start
    - Guaranteed to run to completion
    - Never preempted and killed
  - QUEUEABLE
    - Executed opportunistically
    - Can be queued
    - Not guaranteed to start
    - Not guaranteed to run to completion
- Mercury runtime can access all the resources independently
- Two abandoned alternatives
  - GUARANTEED tasks to distributed:require costly consensus building or forfeiting R2
  - QUEUEABLE tasks to centralized: burden for the centralized scheduler(on single node) is too heavy

## Architecture
- Composed by 2 sub-sys: runtime& resource management framework
- Application master sends request to mercury runtime
- Mercury runtime route request to corresponding scheduler depends on its type
  - Type can be assigned by application policy
- Centralized / Distributed Scheduler makes decisions and responds back to runtime with access to the node

## Container Allocation
- GUARANTEED containers are allocated by the central scheduler
  - Centralized container masters the knowledge of entire resource cluster
- To support fast container allocation, a distributed scheduler restricts itself to allocating QUEUEABLE containers, which can be placed on any machine in the cluster.
  - The distributed scheduler uses lightweight cluster load information, provided by the Mercury Coordinator

## Task Execution
3 cases
- G-G: not possible, because the decisions are made by centralized scheduler(on a dedicated node)
- G-Q: Q will wait
- Q-Q: invent priority improve job-level latency

What's more, Mercury supports leveling up from Q to G

## Framework polices
### Invariant Enforcement Policies
- For GUARANTEED containers
- Quota for QUEUEABLE

### Placement polices
- GUARANTEED
  - Sufficient resources
- QUEUEABLE
  - Run-time estimates

### Load Shaping
- Dynamically rebalancing load across nodes
- Queue reordering
- Resource Policing: minimize killing

## Application level polices
- Time bound
- Probability (or rate) of assigned distributed way meets the constraints about time bound
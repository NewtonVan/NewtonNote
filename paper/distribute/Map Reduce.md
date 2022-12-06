#google #classic 

Background
---
- Problem to solve
  - Complexity
  - Distributed data, parallelization of the computation
  - Large scale, parallelization, fault tolerance, local optimization
- Usage
  - Large clusters of commodity PCs connected together with switched Gigabit Ethernet

Idea & Motivation
---
- Propose abstract programming model.
  - Map & Reduce
  - A large variety of jobs can be expressed in this model
- Network bandwidth is a scarce resource.
- Active disks, where computation is pushed into processing elements that are close to local disks, to reduce the amount of data sent across I/O subsystems or the network.
- Fault tolerance problems are always left to programmers to manage themselves.

Design & Implementation
---
1. Workflow overview
  1. Input data assigned by master, processed by workers.
  2. Intermediate result is written to local disk.
  3. Map task turn the original kv domain into new domain
  4. Reduce collect the intermediate result to calculate the final output.
  5. Reduce job output the final result into a global file system.
2. Master data structure
  1. Identity of worker machine
  2. state
  3. For every map task, location and size of R intermediate file regions produced by map tasks.
1. Updates to this location and size information are received as map tasks are completed. The information is pushed incrementally to workers that have in-progress reduce tasks

3. Fault tolerance
  1. Handling worker failures
    1. Heart beat
      1. Inprogress, failed, reset to idle
      2. Completed map, failed, reset to idle
      3. Resilient to large-scale worker failures
    2. Map task completed, lose connection, reexcute
      1. Result of map task is written to local disk
    3. Reduce task completed, no need to reexute
      1. Result written into global file system
  2. Semantic in presence of faliure
    1. Deterministic: nonfaulting sequential, atomic commits
      1. Map: first, record size and location; else, ignore
      2. Atomic renaming: underlying file system
    2. Non-deterministic: weaker but reasonable
  3. GFS
4. Locality
  1. Network bandwidth in a cluster is a scarce resource
  2. Local disk significantly reduces the IO throughput
5. Task Granularity
  1. More M and R(number of tasks) is better
    1. Dynamic load balancing
    2. Speed up recovery
    3. Todo ? why?
  2. Practically upper bound
    1. master data structures are in memory, complexity is $O(M+N)$, schedule decisions; $O(M*N)$task state
    2. Number of reduce task is relevant to user jobs. Output of every reduce job ends up a separate output file

Experiment
---
- No need to say too much, it's so successful.


Origination of many dis-aggregated architecture.

# Background
- Monolithic server architecture suffers from lots of bottleneck in the distributed situation

# Target
- Decouple os functionality loosely
- Improve the elasticity of cluster
- Build a prototype of split kernel


# Motivation
## Existing Defects
Monolithic architecture has following shortcoming upon our goal
- Low resource utilization
- Poor hardware elasticity
- Coarse failure domain
- Bad support for heterogeneity

## Gap
There is an emerging interest in utilizing resources beyond a local machine [41], such as distributed memory [7, 34, 74, 79] and network swapping [47]. These solutions improve resource utilization over traditional systems. However, they cannot solve all the issues of monolithic servers (e.g., the last three issues in §2.1), since their hardware model is still a monolithic one. 
- Existing OS and distributed system can't work well with new architecture
![[Pasted image 20221207163803.png]]
- Single-node OS take server as the unit of management
  - Numa try to fix this. High network latency and bandwith. 
- Multi-kernel running a kernel on each core/device using msg passing. 
  - All access some common haredware resources
  - Do not manage distributed resources or handle failures
We summarize the following key challenges in building an OS for resource disaggregation, some of which have previously been identified [40].
• How to deliver good performance when application execution involves the access of networkpartitioned disaggregated hardware and current network is still slower than local buses?
• How to locally manage individual hardware components with limited hardware resources?
• How to manage distributed hardware resources?
• How to handle a component failure without affecting other components or running applications?• What abstraction should be exposed to users and how to support existing datacenter applications?

## Source of inspiration
- Dis-aggregated storage
- Faster and scalable network(RDMA)
- Network interfaces are moving closer to hardware components
- Hardware devices are incorporating more processing power.

# Design
## Idea
- Propose split-kernel architecture
- Decouple OS functionality separately and loosely
- Run monitors on hardware components
- Messaging mechanism across non-coherent componnets
  - runs on general-purpose network layer
  - maintaining coherence for our targeted cluster scale would cause high network bandwidth consumption.
- Global resource management and failure handling.
- Stateless

## Abstraction & Usage model
- Expose a set of distributed set of virtual nodes
  - A vNode can run on multiple components
  - One component can host resources for multiple vNodes
- Does not support writeable shared memory across processors
  - This simple design gets lots of benefits in detailed design.
Applications that use shared writable memory across processes (e.g., with MAP SHARED) will need to be adapted to use message passing across processes.

One of the initial decisions we made when building LegoOS is to support the Linux system call interface and unmodified Linux ABI, because doing so can greatly ease the adoption of LegoOS. D

## LegoOS architechture
- A prototype for split-kernel model
- Disseminate functionalities into moniters
- Monitor host on component
  - Process
    - Processor virtual caches(Excache)
  - Memory
    - Storage cache
  - Storage
- Resource management follows 2 level style. 
  - Global management focuses on coarse // todo
  - Local management execute detailed management

## P management
- In every pComponent, using a simple local model.
- No scheduling or kernel preemption under common scenarios
  - Minimizing context switch cost
- Small amount cores dedicated to kernel backbround threads

## M management
![[Pasted image 20221207163855.png]]
- Split into vRegion
  - Coarse-grained
  - Fix-sized
  - Only one component owns vRegion
  - Owner handles all request and access
  - Lower level stores vma which managed by owner

Allocation flow
1. pComponent forward request to home mComponen.
  1.  Home mComponent find the mComponents fit the request
  2. No active component fits, interact with GMM to allocate mComponent, find a candidate own new vRegion
2. Home forward request to the candidate if it's not candidate
  1. performs local virtual memory area allocation and sets up the proper vma tree.
3. pComponnet direct interact with candidate

# Todo
- [ ] Interruption across network?
  - [ ] 4.3.1 is that necessary?

# Reference
- 操作系统模型与乐高积木 · OSDI '18 - 面向信仰编程
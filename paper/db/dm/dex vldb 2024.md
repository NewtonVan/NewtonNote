Time Cost: min
# Background
## Scenarios
DM Range Indexes.

## Current Defects
1. Not scalable => Hidden storage hierarchy => rdma non-trival latency
2. insufficient local & remote resource schedule


# Requirements
alleviate RDMA cost

# Motivation
## Gap 
1. frequent rdma acess
	1. improper monolithic design doesn't fit DM
2. coherence need heavy rdma atomic
3. non-trivial RDMA cost

## Opportunities & Inspiration
1. Local & Remote IO cost become narrower than legacy archetecture.
2. Limited remote CPU resource can be used to reduce RDMA access


## Challenges
1. rudimentary cache
2. unprincipled offload
3. excessive inconsistency


# Design
## Core idea
1. logical partioning
2. compute cache
	1. pointer swizzling
	2. cooling map eviction
	3. path aware caching
3. opportunistic offloading
	1. load and cost aware offloading

## Architecture

## Recovery

# Experiment
## Design Intention
* Performance and Scalability
* Verify effectivity of Compute Cache & Offloading
* Sensibility (cache size, remote compute power)

# Todo


# Reference

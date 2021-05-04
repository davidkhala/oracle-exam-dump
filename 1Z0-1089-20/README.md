


## General
- BM.2.36, 36 cores per node took 4 hours. 4 nodes took 3 hours. What is the efficiency? 
    - Efficiency = Time ratio/Core ratio
    - Efficiency 1 = 4 / 36 = 1/9
    - Efficiency 2 = 3 / 4
- For creating a file system with higher performance block volume, what minimum block volume size would you choose for highest throughput for 1MB block size 
    - Throughput (MB/s) = IOPS * Block Size
- Need to store 3TB of data how do you store it to maximize the throughput
    - Block size could be 1Byte, 4kByte, 1MByte. Default is 4kByte
- When would you use HPC
    - [x] Computational Fluid Dynamics
    - [x] Monte Carlo Risk Analysis
- Which is an accurate analogy for Amdahl's law?
    - [ ] There Is no such thing as a free lunch.
    - [ ] An orchestra can only play well together If they have a great conductor.
    - [x] When chopping vegetable to prepare a 4 person-meal, 2 persons are going twice as fast as one, but 8 people may not be 8 times faster.
    - [ ] In track and field, the 4xl00m relay is only 17% faster than the world record for individual 400m.

- Which Message Passing Interface (MPI) distribution is NOT available today?
    - [ ] Intel MPI
	- [ ] Open MPI
    - [ ] IBM Platform MPI
    - [x] OCI MPI
- Why 32 PPN (32 CPU Core) is running faster than 36 PPN?
    - MPI
- If one of the MPI node failed, what need to do in order to re-run the job automatically?

## Compute
- What do you need to do when you provision an OEL image from market place? 
    - Install vnc, SSh key, related packages 
- Shape to use for monte carlo analysis
- What frequency required for monte carlo?
    - 1 core turbo, all core turbo?

## Network
- Load balancing algorithms
    - round robin, least connectivity, IP hash 
- Load Balancer Protocol
    - TCP/HTTP
- Load Balancer Shape on OCI
- The latency between 2 BM.HPC2.36 nodes using RDMA on the same rack  
    - Expected latency intra-rack is ~1.7us
    - There is a RDMA latency test table and ask if this is normal. Not sure if we get right, we just use common sense 1.7us for same rack and 3us for across rack.
   
- What security list required for subnet 1(bastion-public access) and subnet 2(BM-private access) with limited access?    
    - port 22
- CIDR Range
- Cluster networking built on top of 
    - Instance pools  
## Storage
| Performance Level | IOPS/GB | Max IOPS/Volume | Throughput/GB | Max Throughput/Volume | VPUs/GB |
| ----              | ----      | ----          | ----          | ----                  | ----      |
| Lower Cost | 2                | 3000          | 240           | Up to 480             |   0       |
| Balanced  |   60              |   25000       |   480         |   480                 | 10        |
| Higher Performance|   75      | 35000         |   600         | 480                   | 20        |

- How are instances distributed in an instance pool?
    - Distributed across all fault domains in a best-effort manner based on capacity.
- What is the sequence to delete instance in instance pool? 
    - Instance, boot volume, block volume
- HDFS replication factors
    - 2 for low risk and 3 standard
- There is a case to ask if Replication factor changed from 1 to 2, will it impact the throughput
    - Read / write / Read+Write
- What performance benchmark not use for a Linux Filesystem?
    - [ ] IOR
    - [ ] IO500
    - [] iPerf
    - [x] fio
    - [x] Vdbench
- store a large amount of data where most of it does not need to be accessed frequently
- Different types of storage available to build file system on OCI 
    - HPC compute Shapes with NVMe/DenseIO, Block Vol
- What file system should be used to allow multiple compute instances to read/write data concurrently without any data loss
    - Parallel file system
    - Lustre & Distributed file system
    - Gluster
- What is the sequence to consider when creating Max Throughput IO ?
    - Network->Storage->CPU/RAM 
    - ??

## Operation
- In a job, nodes are known to fail, what should you do?
    - Rerun the job
- How should you double the capacity of a 3000 core cluster
    - Instance pool
- Type of Autoscaling supported by OCI
    - Metrics based
    - Schedule
- What performance metrics support for metrics base autoscaling? 
    - CPU Utilization
    - Memory Utilization
- Instance pool scaling mechanism
    - balance across AD, FD
- Metrics to keep track of file system
    - throughput
    - latency
## Big Data
- What are the challenges for customer running Big Data on Prem?
- Big Data Migration Best Practice
    - Object storage
- Common Big Data Workload
    - In memory
    - batch processing 
- What Big Data solution can run Spark workload
    - Oracle Data Flow (ODF) 
- What notebook is used in Data Science Platform
    - Jypter
- What data source supported for Data Science Cloud Service?
    - ADE??
    - OCI Object Storage, AWS S3, Azure Blog, Google Object Storage
- What Hadoop commerial dist. Supported on OCI
    - Cloudera
    - Hortonworks
    - MapR
- What is Terasort
    - TeraSort is a popular benchmark that measures the amount of time to sort 1 terabyte of randomly distributed data on a given computer system. It is commonly used to measure MapReduce performance of an Apache Hadoop cluster.
- What does Data Science integrate with
    - ADW, Oracle Functions, Object storage 
- Steps when using Data Science
    - Data acquisition, feed
    - Explore Data
    - Analysis


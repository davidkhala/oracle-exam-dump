

## General
- A customer ran a Job on 2 BM.HPC2.36, and the job took 4 hours using 32 cores of each node. They later ran on 4 nodes and the Job took 3 hours. What Is the efficiency gained?
    - [ ] 100%
    - [x] 66%
        - This means the improvement ratio, current / previous
    - [ ] 75%
    - [ ] 50%

-  You've run a task on Oracle Cloud Infrastructure (OCI)
    > BM Standard E3 128:   4h
    > BM HPC 2.36:          4h
    > BM Standard E3 2.52:    6h
    > BM GPU3.8             2h
    What is the most cost effective option
    - [ ] BM GPU3.8
    - [ ] BM Standard2.52
    - [ ] BM Standard E3.128
    - [ ] BM HPC2.36
- You are building a file system that needs to handle large files with a lot of nodes reading at the same time.
    What should be your main goal?
    - [ ] Minimize latency
    - [ ] Maximize Latency while keep throughput above a certain threshold
    - [ ] Minimize throughput while keeping the latency low
    - [x] Maximize throughput
- Which two types of workloads can benefit from Cluster Networking (RDMA)
    - [x] Computational Fluid Dynamics
    - [x] Monte Carlo Risk Analysis
    - [ ] Movie Rendering
    - [ ] HPC File Server
- Which is an accurate analogy for Amdahl's law?
    - [ ] There Is no such thing as a free lunch.
    - [ ] An orchestra can only play well together If they have a great conductor.
    - [x] When chopping vegetable to prepare a 4 person-meal, 2 persons are going twice as fast as one, but 8 people may not be 8 times faster.
    - [ ] In track and field, the 4xl00m relay is only 17% faster than the world record for an individual 400m.

- Which Message Passing Interface (MPI) distribution is NOT available today?
    - [ ] Intel MPI
	- [ ] Open MPI
    - [ ] IBM Platform MPI
    - [x] OCI MPI
- You are running a cluster using multiple BM.Standard2.52 machines. The model is on a NFS share running on block volume. You've tried doubling the number of machines but it's not runing any faster. 
    Which two actions could potentially speed up this tightly coupled workload
    - [ ] Switch to FSS for your file system.
    - [x] Use Cluster Networking
    - [x] Use BM.HPC2.36
    - [ ] Switch to ESS mode

- You've spun up a GPU instance with the standard OEL image (GPU version) from the console network on Oracle Cloud Infrastructure (OCI)
    What action do you need to do in order to be able to visualize your desktop remotely.
    - [ ] Install Open MPI for distributed GPU access.
    - [x] Install a desktop and VNC server
    - [ ] Install NVDIA drivers
    - [ ] Open a remote serial console
- Which workload is massively parallel in nature
    - [x] Map/Reduce
    - [ ] SQL Queries
    - [ ] ETL
    - [ ] Streaming
## Compute
- When running a high memory workload, what should be your machine of choice?
    - [x] BM Standard E3 128
        - Up to 2048 GB RAM https://docs.oracle.com/en-us/iaas/Content/Compute/References/computeshapes.htm#baremetalshapes__bm-standard
    - [ ] BM Standard E2 64
    - [ ] BM HPC 2.36
    - [ ] BM GPU 3.8
- You are comparing different processors for Monte Carlo simulation with millions of single core execution. What frequency will have the highest impact on the "time to solution" 
    - [ ] Turbo frequency
    - [x] All core turbo frequency
        - kenneth choice
    - [ ] Only the network throughput will influence Monte Carlo simulations
    - [ ] Base frequency
- You have two different workloads, workload 1 does not scale very well (~100 cores) and requires a very high memory bandwidth, and a workload 2 that Is compute bound and IO intensive.
    Which Instances should you select?

    - [ ] 1: BM.HPC2.36 2: BM.Standard.2.52
    - [x] 1: BM.Standard.E3.128 2: BM.HPC2.36
    - [ ] 1: BM.HPC2.36 2: BM.Standard.E3.128
    - [ ] 1: BM.Standard2.52 2: BM.HPC2-36
- What would you use to run an embarrasingly parallel workload for risk analysis with Monte Carlo?
    The code is homegrown and has not changed much in the last decade. They will use a parallel file system outside of the compute cluster
    - [ ] BM.GPU3.8
    - [x] BM.Standard.E2.64
    - [ ] BM.DenseIO2.52
        - equipped with local NVMe
    - [ ] BM.HPC2.36
        - equipped with local NVMe
- A customer has decided to user Oracle Cloud Infrastructure
    ... RPO 4 hours, and an RTO of 1 hour
    Which two options should they consider on OCI to meet
    - [ ] Replicate data to OCI Object Storage in near-realtime
    - [x] Replicate data to a Haddoop cluster running on OCI in near-realtime
    - [ ] Use Terraform to rapidly provision Hadoop Cluster on OCI
    - [x] Replicate data to OCI Object Storage every hour
## Network
- A Linux visualization instance in the public subnet with Security List 0.0.0.0 for TCP port 22
    What other rule do you absolutely need to be able to connect remotely.
    - [x] No other additional rules are needed.
    
- Which three are available on Oracle Cloud Infrastructure (OCI) as load balancing policies?
    - [x] Least Connections
    - [x] Round Robin
    - [ ] Random
    - [ ] Least CPU Utilization
    - [x] IP Hash
- Which two options are valid when configuring health check ... in Load Balancer?
    - [ ] FTP level health checks
    - [x] TCP level health checks
    - [ ] UDP level health checks
    - [x] HTTP level health checks
- Which of the following is NOT a valid OCI load balancer shape? Select one.
    - [ ] 10 Mbps
    - [ ] 100 Mbps
    - [ ] 400 Mbps
    - [x] 1000 Mbps
    - [ ] 8000 Mbps
- What is (roughly) the latency between 2 BM.HPC2.36 nodes using RDMA on the same rack?
    - [ ] 1.7 nano seconds
    - [x] 1.7 micro seconds
        - Expected latency intra-rack is ~1.7us
    - [ ] 3 micro seconds
        - the latency between 2 nodes using RDMA on a different rack is 3 microseconds
    - [ ] 0.2 milli seconds
   
- You have an HPC cluster running tightly coupled MPI jobs without VPN or Fast Connect.

    The compute nodes are on subnet2(172.16.1.0/24), and there is a BM.Dense.I02.8 on subnet1 (172-16.0.0/24) that will serve as a bastion and file server.

    What security lists should you choose to be able to run the workloads while limiting access as possible?
    - [x] Subnet1: 0.0.0.0 for TCP port 22, subnet 1 and 2: 172.16.0.0/23 for all TCP/UDP ports
    - [ ] Subnet1: 0.0.0.0 for all protocols, subnet2: 172.16.0.0/16 for all protocols
    - [ ] Subnet1: 172.16.1.0/24 for port 22, subnet2: 172.16.1.0/24 for all protocols
    - [ ] Subnet1: 0.0.0.0 for TCP port 22, subnet 7: 172.16.0.0/16 for TCP port 22
- CIDR 172.16.0.0/16, which following is included
    - [x] 172.16.32.0/23
        - 172.16.32.0 ~ 172.16.33.255
    - [ ] 172.16.32.0/16
        - This is same with 172.16.0.0/16
    - Hints：CIDR 172.16.0.0/16 --> 172.16.0.0 ~ 172.16.255.255
- What are cluster networks built on?
    - [ ] Built on top of instance pools feature
## Storage
- A file system is built using BM.Standard2.52 Compute shape for File Servers.
    One 25 Gbps vNIC/network card is used to connect to 10 Block Volumes of 1TB each (max. 480MB/s per volume). The other 25 Gbps vNIC is used for sending/receiving data to/from client
nodes. File system client instances who mount the file system are provisioned using VM.Standard2.16 Compute shapes. 
    What is the max IO theoretical throughput a client node can get?
    - [ ] 3125 MB/s
    - [x] 2050 MB/s
    - [ ] 4800 MB/s
    - [ ] 6250 MB/s

- A file system is built using two BM.Standard2.52 Compute shapes for File servers. On each file server, one 25 Gbps (3125 MB/s) NIC/network card is used to connect to 10 Block Volumes of 1TB each (max. 480MB/s per volume) and other 25 Gbps NIC Is used for sending/receiving data to/from client nodes.
    File system client instances which mount the file system are provisioned using VM.Standard2.16 Compute shapes. (Network bandwidth: l6.4Gbps(2050 MB/s))
    What is the max aggregate IO throughput (theoretical) of the file system?

    - [ ] 6250 MB/s
    - [x] 4800 MB/s
    - [ ] 3125 MB/s
    - [ ] 9600 MB/s
- What minimum size of block volume with **Balanced performance tier** maximizes throughput for large files
    - [ ] 10 TB
    - [x] 1 TB
    - [ ] 32 TB
    - [ ] 100 GB
- Needs to handle large files with a lot of nodes reading at the same time. 
    Which minimum size of block volume maximizes the throughput
    - [x] 800 GB
        - From 800GB ~ 32TB. The Max Throughput is same for all volume size.
        - Higher performance scenario
        - https://docs.oracle.com/en-us/iaas/Content/Block/Concepts/blockvolumeperformance.htm#Higher_Performance
    - [ ] 1 TB
    - [ ] 10 TB
    - [ ] 500 GB 
- How are instances distributed in an instance pool?
    - [x] Distributed across all fault domains in a best-effort manner based on capacity.
- On Oracle Cloud Infrastructure (OCI), a customer wants to build a 3TB filesystem for high throughput oriented workloads
    which action provides the highest IO throughput using OCI block volumes for storage?
    - [ ] Attach one Block volume of 3TB volume size and use filesystem Block size of 256k or lower
    - [ ] Attach one Block volume of 3TB volume size and use filesystem Block size of 1M or higher
    - [ ] Attach three Block volume of 1TB each and use filesystem Block size of 256K or lower
    - [ ] Attach three Block volume of 1TB each and use filesystem block size of 1M or higher

- A two node clustered/parallel filesystem built using Baremetal Compute shape (BM.Standard2.52) and Block Volume Storage delivers maximum sustained aggregate IO throughput of 5GB/s for read and write, while storing a single copy of the data (replica=l) in filesystem.

    What will be the maximum sustained aggregate IO throughput for read and write, when two copies of the data (replica=2) are stored in filesystem for High Availability?
    - [ ] 5GB/s for both (read and write)
    - [ ] 2.5GB/s for read and 5GB/s for write
    - [x] 2.5GB/S for write and 5GB/s for read
        - Kenneth choice: read throughput will not be affected by replica number
    - [ ] 2.5GB/s for both (read and write)
- What performance benchmark not use for a Linux Filesystem?
    - [ ] IOR
    - [ ] IO500
    - [x] iPerf
    - [ ] FIO
    - [ ] Vdbench
- A customer wants to store small files (KBs) workload in a file system. 
    What two options should you use to measure performance for this system.
    - [ ] CPU processor clock speed for faster processing
    - [ ] Amount of Memory on file servers
    - [x] High IOPS
    - [x] Low Latency
- A customer has a very busy workload. The model is very large (1 PB range) and only some small files are updated for new jobs. Throughput needed during the run is roughly 25GB/s.

    What is a fast and cost-conscious way to handle the file system?

    - [ ] Put the data in object storage, and mount It using s3fs-fuse project.
    - [x] Build a file-system using NVMe on Dense shapes. Then move the data to object storage when not needed.
    - [ ] Build a file system using Block volumes and Standard BMs, take advantage of the different block volume performance levels.
    - [ ] Use NVMe on HPC shapes to build a File System with the RDMA connection.

- What are two different types of Storage offerings available to build a filesystem on Oracle Cloud Infrastructure (OCI)?
    - [x] Local NVMe SSDs on DenseIO and HPC compute shapes
    - [x] Block Volume Service
    - [ ] File Storage
        - File Storage service is the partitioned & formatted result of block volume, always have inferior performance than block volume
    - [ ] Object Storage

- OCI Block Volume Storage supports sharing a Block Volume among multiple compute instances in read/write or read-only shareable mode. 
    What file system should be used to allow multiple compute instances to read/write data concurrently without any data loss?
    - [x] Parallel File Systems like Lustre, IBM Spectrum Scale(GPFS), BeeGFS, etc
    - [ ] Linux File Systems like XFS, EXT4, EXT3, etc
    - [ ] Network File System (NFS)
    - [x] Distributed File Systems like Gluster, OCFS2, GFS2
- You are building a large filesystem to maximize throughput of large files using high performance block volume and BM standard2.52 as file servers. 
    Which block volume configuration should you choose to ensure aggregate block volume throughput is higher than network bandwidth of file servers.
    - [ ] 7 Block Volumes of 800 GB
    - [x] 32 Block Volumes of 800 GB
        - Kenneth Choice: 800 GB have reached the largest max thoughput per volume
    - [ ] 5 Block Volumes of 32 TB
    - [ ] 6 Block Volumes of 32 TB

- You are architecting the infrastructure for a file system.
    What are the different criteria you should use, and in what order to build a filesystem for optimal performance?
    - [ ] Network Bandwidth > Number of Compute Cores/RAM > Storage
    - [ ] Storage > Network Bandwidth > Number of Compute Cores/RAM
    - [ ] Number of Compute Cores/RAM > Storage > Network Bandwidth
    - [x] Network Bandwidth > Storage > Number of Compute Cores/RAM
        - Kenneth choice: compute/RAM is not related to filesystem
- You are building a file system of 10TB Storage Capacity
    Volume Storage. Balanced Elastic Performance 
    Which two options are correct about how many block volumes
    - [x] 10 Block Volumes of 1TB size
    - [ ] One Block Volume of 10TB size
    - [ ] 20 Block Volumes of 500GB size
    - [ ] 8 Block Volumes of 1.25TB size

## Operation
- On a RDMA cluster, a latency test was conducted
    | Node1 |Node2| Latency (micro-seconds)|
    | ---- | ---- | ---- |
    | 1 | 2 | 1, 74 |
    | 1 | 3 | 1, 78 |
    | 1 | 4 | 3, 1 |
    | 2 | 3 | 1, 74 |
    | 2 | 4 | 3, 08 |
    | 3 | 4 | 3, 11 |     
    What should you do
    - [ ] Report the higher latency througha SR
    - [x] Rerun the test and see if it is consistent
    - [ ] Latency is not critical, check the bandwidth
    - [ ] Nonthing, the behavior is normal
    
- Which statement is correct about deleting an instance pool
    - [x] Instances and block volumes will be deleted
        - When you delete an instance pool, the resources that are associated with the pool are permanently deleted. This includes instances that were created by the pool, instances that are attached to the pool, attached boot volumes, and block volumes.
        - https://docs.oracle.com/en-us/iaas/Content/Compute/Tasks/deletinginstancepool.htm
    - [ ] Associated instances and attached boot volumes will be deleted. block volumes will be detached
    - [ ] Nothing will be deleted
    - [ ] Instances and boot volumes will be deleted
    - [ ] Only the instances will be deleted
- What are the two types of autoscaling available on OCI? Select two.
    - [ ] Load based autoscaling
    - [x] Metrics based autoscaling
    - [x] Schedule based autoscaling
    - [ ] Fault based autoscaling

- What are the three components for configuring autoscaling on Oracle Cloud Infrastructure (OCI)
    - [x] Monitoring is enabled on the instances in the instance pool
    - [x] The instance pool supports the maxinum number of instances that you want to scale to. 
    - [x] You have an instance pool
    - [ ] You have a load balancer
    - [ ] You have Bare Metal instances 
- Which two performance metrics can be used to trigger scaling actions in autoscaling? 
    - [ ] Disk IOPS
    - [ ] Network throughput
    - [ ] Network latency
    - [x] CPU Utilization
    - [x] Memory Utilization
- When an instance pool scales in, what is the correct order that the instances are terminated?
    - [ ] The number of instances is balanced across availability domains, the oldest instance within the fault domain is terminated, the number of instances is balanced across fault domains.
    - [x] The number of instances is balanced across availability domains, the number of instances is balanced across fault domains, the oldest instance within the fault domain is terminated.
    - [ ] The oldest instance within the fault domain is terminated, the number of instances is balanced across availability domains, the number of instances is balanced across fault domains.
    - [ ] The number of instances is balanced across fault domains, the number of instances is balanced across fault domains, the oldest instance within the fault domain is terminated.

## Big Data
- Which is a common business problem for customers running Big Data workloads?
    - [x] Cost associated to process a large scale data set
    - [ ] Cost associated with Disaster Recovery for large deployments
    - [ ] Ability to process a small data set at the minimum cost as possible
    - [ ] Ability to process a large data set at the maximum cost as possible
- What are some best practices for Big Data Migration?
    - [x] Object storage
    - [x] Data Transfer Appliance
    - [x] FastConnect

- Which two Oracle Cloud Infrastructure (OCI) shapes are a good choice for Spark workload
    - [ ] BM.Standard
    - [ ] HPC
    - [ ] VM.Standard
    - [ ] GPU
- What Big Data solution can run Spark workload
    - [x] Oracle Data Flow
    - [ ] Self-managed Hadoop deployment
    - [ ] Self-managed Spark deployment
    - [ ] Big Data Service
- Which is NOT an advantage associated with moving a Big Data workload to Oracle Cloud Infrastructure (OCI)?
    - [ ] managed service offerings to support common Big Data workloads
    - [ ] best price / performance for Big Data workloads In the Cloud
    - [x] availability of Oracle Airflow
    - [ ] Object Storage as Data Lake
    - [ ] dynamically scale capacity against workload
### Oracle Data Science    
- Which three data sources supported for Oracle Data Science?
    - [ ] Autonomous Data Warehouse
    - [ ] On-premises Oracle Database
    - [x] AWS S3 bucket
    - [x] Azure Blog
    - [x] Google Object Storage
- Which statement is NOT correct?
    - [x] Oracle Data science is augmented with AI VM(??) for Data science
    - [ ] Oracle Data science is not excluded from Universal Credit
    - [ ] Oracle Data science can integrate with Oracle Function.
        - (Oracle Data Science) Integrates with the rest of the OCI stack, including Functions, Data Flow, Autonomous Data Warehouse, and Object Storage.
    - [ ] Oracle Data science does not support per second billing

- Which statement correctly describes Oracle Data Science
    - [x] It enables data science teams to build, train and manage machine learning models on Oracle Cloud
    - [ ] It provides management for on-premise machine learning models
    - [ ] Oracle's Data Science model catalog holds contains only the model artifact
    - [ ] It is primarily focused on supporting a single data scientist

### Hadoop    
- Which Hadoop distributions are supported on OCI?
    - [ ] Apache Hadoop
    - [x] Cloudera
    - [x] Hortonworks
    - [x] MapR
    - [ ] Pivotal EMC
- What does TeraSort phase of TeraSort benchmark do?
    - [ ] It maps and reduces source data in parallel manner, leveraging data locality to minimize network transfer
    - [ ] It randomly maps source data and reduces output to a smaller data set.
    - [x] It maps and reduces one terabyte of data into a smaller data set
    - [ ] It randomly maps source data and increases output to a bigger data set.
- Which two Oracle Cloud Infrastructure (OCI) storage options are supported for direct HDFS use in Hadoop?
    - [ ] Object Storage
    - [x] Block Volume
    - [x] DenseIO NVMe
    - [ ] FSS
- What HDFS replication factor should be used for locally attached storage in HDFS?
    - [ ] 1
    - [ ] 2
    - [x] 3
        - This is the answer from the Practise Exam
    - [ ] 4
- What HDFS replication factor can be used with Block Volumes to optimize cost?
    - [ ] 1
    - [x] 2
    - [ ] 3
    - [ ] 4 
## Potential
- Which of the following shapes are available for Data Science Notebook Sessions?
    - [ ] BM.GPU2.1
    - [x] VM.Standard2.1
    - [ ] BM.GPU3.8
    - [x] VM.Standard2.16
        - https://quizlet.com/522060200/hpcbig-data-certification-flash-cards/
- Which one is the correct progression of steps when using Accelerated Data Science?
    - [ ] Data Acquisition ---> Feature Engineering ---> Exploratory Data Visualization ---> Model Training
    - [ ] Data Acquisition ---> Hyperparameter optimization ---> Feature Engineering ---> Model Training
    - [x] Data Acquisition ---> Exploratory Data Analysis and Visualization ---> Feature Engineering ---> Model Training
    - [ ] Data Acquisition ---> Feature Engineering ---> Model Training---> Exploratory Data Analysis and Visualization



- Which benchmark is important to a customer when considering Big Data workloads on Oracle Cloud Infrastructure (OCI)?
    - [x] TPC-DS
        - TPC-DS is the de-facto industry standard benchmark for measuring the performance of decision support solutions including, but not limited to, Big Data systems. 
    - [ ] TPC-DI
    - [ ] TPC-C
    - [ ] Terasort

# Architecture

## Cluster architecture

HPC is often equated with a cluster computer, a collection of computers linked together over a high-speed network to perform highly complex computing tasks. These connected computers (usually called *servers*) work together to provide the processing power to analyze and process large data sets, simulate complex systems, and solve complex scientific and engineering problems.


```{figure} ../img/architecture-shematic.png
:height: 12cm
An overview of the HPC cluster architecture.
```

```{callout} The main components of the HPC cluster
- **compute** - a collection of computers or servers that are the main power of the computer cluster.
- **memory** - high-speed and high capacity memory and storage systems for handling large amounts of data.
- **network** - high-speed network systems that connect all parts of the cluster together
```

<!--
```{figure} ../img/architecture-Raj.png
An overview of the HPC cluster architecture on the example the Raj HPC system at Marquette University.
Figure taken from [https://www.marquette.edu/high-performance-computing/architecture.php](https://www.marquette.edu/high-performance-computing/architecture.php)
```
-->



## Compute

The computer cluster consists of a large number of compute nodes (machines) organized in blades and racks. Multiple racks make a computer cluster.

```{figure} ../img/hpc-architecture.png
:height: 8cm
The supercomputer is built of the number of compute nodes
```

Modern HPC systems are hybrid computing systems equipped with a conventional CPU (AMD or Intel) and various accelerators. Nowadays, the dominant accelerators are graphics processors (Nvidia and AMD), but also [FPGA](https://simple.wikipedia.org/wiki/Field-programmable_gate_array), Many Integrated Core (MIC) from Intel (e.g. [Xeon Phi](https://en.wikipedia.org/wiki/Xeon_Phi) - discountinued), and Tensor Processing Units ([TPU](https://en.wikipedia.org/wiki/Tensor_Processing_Unit)).

To improve the energy efficiency and scalability of HPC systems that consume a lot of electric power, ARM processors are becoming increasingly popular in the HPC world. An example are the Fujitsu [A64FX](https://www.fujitsu.com/global/products/computing/servers/supercomputer/a64fx/) processor, the SiPearl [Rhea](https://sipearl.com/en) or NVIDIA [Grace](https://developer.nvidia.com/blog/nvidia-grace-cpu-superchip-architecture-in-depth/).

```{figure} ../img/supek-gpu-server.png
:height: 12cm
An example of the hybrid CPU-GPU computer server. Supercomputer Supek at the University Computing Centre in Zagreb.
Picture taken from [https://wiki.srce.hr/display/NR/Arhitektura+Supeka](https://wiki.srce.hr/display/NR/Arhitektura+Supeka).
```

## Memory

The memory in modern HPC (and every other) systems is a structured in different levels each with different type, speed and capacity. 

```{challenge} Do you know why there are multiple types and levels of memory?
```

The goal of the memory hierarchy is to provide fast access to frequently used data while maintaining large storage capacities for less frequently accessed data. This hierarchy is critical for optimizing performance in HPC systems, where data access patterns and computational intensity vary widely across workloads.

```{figure} ../img/Memory-Hierarchy.jpg
:height: 12cm
Picture take from [https://computerscience.chemeketa.edu/](https://computerscience.chemeketa.edu/cs160Reader/ComputerArchitecture/MemoryHeirarchy.html)
```

The main memory (also known as RAM - Random Access Memory) in an HPC cluster system or supercomputer is a critical component that directly impacts the performance of computational workloads. It serves as the primary workspace for data that the CPU and accelerators (e.g., GPUs) actively use during computation. The main memory is distributed and visible to only local CPUs and/or GPU (i.e. physical computer or compute node).

**Storage** is a large number of dedicated servers (computers) consisting of a high volume and high read and write speeds. The storage systems are distributed and visible to many (all) compute and login nodes. 
The storage has the following characteristics:
- **Scalability**: highly scalable to accomodate growing data volumes generated and processed by HPC applications.
- **Performance**: ensure that the data can be accessed, read and written at high speeds to keep pace with the computational requirements, support high-performance protocols, such as Parallel File Systems (parallel NFS), parallel IO
- **Parallelism**: support parallel access to data across multiple nodes simultaneously, leverage parallel file systems and distributed storage architectures to maximize throughput and minimize contention.
- **Reliability and Availability**: Secure uninterupted access to data and preventing data loss or corruption, incorporated features such as *redundancy*, *data replication*, *snapshotting*, etc.
- **Security**: Dealing with sensitive or proprietary information, robust security features such as access control, encryption, authentication.

Distributed file systems used nowadays in HPC: [Lustre](https://www.lustre.org/), [GPFS](https://www.ibm.com/docs/en/gpfs/4.1.0.4?topic=guide-introducing-general-parallel-file-s), [Ceph](https://docs.ceph.com/en/latest/start/intro/), [BeeGFS](https://www.beegfs.io/c/).

## Network

The major bottleneck in large scale and data-intensive applications is not computation but the *data movement**! The modern processors can process data at much larger speeds then the data can be transferred (accessed or read) via the network. Therefor, the avaiability of fast interconnections is of paramount performance for HPC applications. 

```{callout} HPC network   
The interconnection inside HPC cluster has to have **high bandwidth** and **ultra low latency**!
```

```{figure} ../img/latency-bandwidth.jpeg
Figure taken from [https://www.dnsstuff.com/latency-throughput-bandwidth] (https://www.dnsstuff.com/latency-throughput-bandwidth)
```

Today, several types of interconnection are predominately used in the HPC systems and these are Infiniband and Ethernet, however, recently interconnect types have emerged such as Slingshot, Omni-Path and Tofu.

```{figure} ../img/interconnect-system-share.png
Graph taken from [https://www.top500.org/statistics/list/](https://www.top500.org/statistics/list/)


## Supercomputers

An extremely large cluster computers comprising of specially designed hardware optimized for parallel processing, including specialized processors such as GPUs, high-speed interconnection and large-scale shared storage systems. Supercomputers usually consists of millions of processing cores and can deliver sustained performance in petaflops.

```{callout} Explore supercomputers (3D virtual tour)
**[Fugaku](https://my.matterport.com/show/?m=2TLoTcWigBf)** - 6th largest supercomputer in the World

**[LUMI](https://360interactive.ade.fi/live/LUMI360/)** - 8th in the World, 3rd in Europe (Finland)
```

<!--
## Types of HPC architecture

## Basic concepts

### Distributed memory system

### Shared memory system

### Bandwidth

### Latency
-->
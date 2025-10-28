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

### Large number of connected computers
The computer cluster consists of a large number of compute nodes (machines) organized in blades and racks. Multiple racks make a computer cluster.

```{figure} ../img/hpc-architecture.png
:height: 8cm
The supercomputer is built of the number of compute nodes
```

Modern HPC systems are hybrid computing systems equipped with a conventional CPU (AMD or Intel) and various accelerators. Nowadays, the dominant accelerators are graphics processors (Nvidia and AMD), but also [FPGA](https://simple.wikipedia.org/wiki/Field-programmable_gate_array), Many Integrated Core (MIC) from Intel (e.g. [Xeon Phi](https://en.wikipedia.org/wiki/Xeon_Phi) - discountinued), and Tensor Processing Units ([TPU](https://en.wikipedia.org/wiki/Tensor_Processing_Unit)).


```{figure} ../img/supek-gpu-server.png
:height: 12cm
An example of the hybrid CPU-GPU computer server. Supercomputer Supek at the University Computing Centre in Zagreb.
Picture taken from [https://wiki.srce.hr/display/NR/Arhitektura+Supeka](https://wiki.srce.hr/display/NR/Arhitektura+Supeka).
```

## Supercomputers

An extremely large cluster computers comprising of specially designed hardware optimized for parallel processing, including specialized processors such as GPUs, high-speed interconnection and large-scale shared storage systems. Supercomputers usually consists of millions of processing cores and can deliver sustained performance in petaflops.

```{callout} Explore supercomputers (3D virtual tour)
**[Fugaku](https://my.matterport.com/show/?m=2TLoTcWigBf)** - 6th largest supercomputer in the World

**[LUMI](https://360interactive.ade.fi/live/LUMI360/)** - 8th in the World, 3rd in Europe (Finland)
```
# Introduction

## History

### 1940-1960s: the first supercomputers
- Military-driven evolution
- First modern computers developed in WWII ([ENIAC](https://www.britannica.com/technology/ENIAC) - Electronic Numerical Integrator and Computer)
  
```{figure} ../img/eniac.jpg
ENIAC in Philadelphia, Pennsylvania. Glen Beck (background) and Betty Snyder (foreground) program the ENIAC in building 328 at the Ballistic Research Laboratory (BRL). Figure taken from [Wikipedia](https://hr.wikipedia.org/wiki/ENIAC).
```

- Cold War: code breaking, intelligence gathering and processing, weapon design
- [ILLIAC-IV](https://en.wikipedia.org/wiki/ILLIAC_IV)
  - Began in 1966; goal was 1 GFLOP/s; estimated cost $8 million
  - finished in 1972 at a cost of $31 million and a top speed far below 1 GFLOP/s 
  
### 1975-1990: the Cray era
- The speed was primarily achieved through two mechanisms:
  - vector processors
  - share memory multiprocessing
- [CRAY-1](https://en.wikipedia.org/wiki/Cray-1) - the first supercomputer to successfully implement the vector processor design.
- The first GFLOP/s supercomputer - [CRAY-2](https://en.wikipedia.org/wiki/Cray-2) (1985). 

### 1990-2010: the cluster era
- More vector processors (>8) results in memory contention -> slows down the computation
- Solution: distributed memory systems where each processor has its own memory.
- first cluster built in 1994 by Becker and Striling at NASA using available PCs and networking hardware (16 Intel 486DX PCs, 10 Mb/s Ethernet, 1 GFLOP/s) - named Beowolf

```{figure} ../img/Beowolf2-300x174.jpg
An example of a Beowolf Cluster. Figure taken from [https://memim.com/beowulf-cluster.html](https://memim.com/beowulf-cluster.html).
```

### 2010-present: the accelerator (GPU) and hybrid era
- Increasing number of processor cores, not processor speeds.
- Development of GPUs and other accelerators.
- Today's supercomputers are hybrid clusters mixed of traditional processors and the accelerators. 


<!--## The roots of HPC in modern science
In modern science there are 3 methodologies: (staviti sliku umjesto list)
  1. Theory
  2. Experimentation
  3. Simulation

- When experimentation is very difficult or even impossible, for example in observing the macromolecular motions, assessing the efficiency of new drugs or describing fission reactions, the simulation can help people to test and prove their theories. Moreover, the simulations can better direct the experimentation phase.

- To keep pace with the scientific and industrial needs the simulations need to be more `accurate` and finish in less time which requires greater computing power

- Single processors cannot deliver that power
  - Making processor with higher clock speed is expensive and impossible due to the heat/power limitations
  - Expensive to put hugh memory on a single processor

```{callout} Solution
Parallel computing - split work into smaller pieces and divide it among numerous linked processors.
```

```{challenge} Challanges of parallel computing
Think of 3 possible challanges if you would have to split and process your work among several linked processors (computers).
```-->

---

## What is HPC?

**High Performance Computing (HPC)** refers to the practice of utilizing **very large computers** (supercomputers, clusters) to perform **computationally** and memory **intensive tasks** at **high speeds** using **parallel processing**.
HPC involves usage of advanced hardware and software to solve extremely complex problem that go beyond the capabilities of conventional computational systems.

What is High-Performance Computing - [YouTube](https://www.youtube.com/watch?v=IniYMq2bJRI&t=1s) (Croatian).

```{figure} ../img/HPC-map-3.png
:height: 12cm
Overview of HPC
```

```{challenge} The main features of HPC
- processing at **high-speeds**
- **parallel and distributed** programming and architectures
- solving **big** and **complex** problems
```

## Why HPC?

- Personal computers often lack the processing power and memory capacity needed.
- High-performance GPUs may not be readily available.
- Large volumes of computational tasks need to be processed.
- Access to a diverse range of specialized software programs is required.
- Seamless access to extensive data repositories and databases is essential.

Many research and engineering problems today are beyond the capabilities of personal computers and even workstations. The US National Science Foundation (NSF) has recognized this and defined the '*Grand Challenges*', the fundamental problems of science and engineering that require high performance computers to solve:
  - Advanced New Materials
  - Prediction of Climate Change
  - Semiconductor Design and Manufacturing
  - Drug Design and Development
  - Energy through Fusion
  - Water Sustainability
  - Understanding Biological Systems
  - New Combustion Systems
  - Astronomy and Cosmology
  - Hazard Analysis and Management
  - Human Science and Policy
  - Virtual Product Design
  - Cancer Detection and Therapy
  - AI and Deep Learning
  

```{callout} The main reason for using HPC
To be able to solve bigger and more complex problems!

You can tackle **bigger problems in the same amount of time** and/or you can solve **the same sized problems in less time**.
```

```{challenge} Where to use HPC?
Think of a task that you cannot currently solve on your local computer, but which could be solved on a supercomputer or computer cluster.
```

<!--
## Parallel machine
```{figure} ../img/Fully-Connected-Network-Topology-diagram.png
Adapted from [Fully Connected Network Topology Diagram](https://www.conceptdraw.com/How-To-Guide/fully-connected-network-topology)
```
In HPC word, each computer in the network is called `compute node`.

- Definition of HPC + concept map
-->
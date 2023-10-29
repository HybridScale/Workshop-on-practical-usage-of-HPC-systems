# High-Performance Computing

## The roots of HPC in modern science
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
```
---

## What is HPC?

**High Performance Computing (HPC)** refers to the practice of utilizing **very large computers** (supercomputers, clusters) to perform **computationally** and memory **intensive tasks** at **high speeds** using **parallel processing**.
HPC involves usage of advanced hardware and software to solve extremely complex problem that go beyond the capabilities of conventional computational systems.

<!--```{figure} ../img/HPC-map-2.png
:height: 12cm
Overview of HPC
```
-->

```{figure} ../img/HPC-map-3.png
:height: 12cm
Overview of HPC
```

<!--
## Parallel machine
```{figure} ../img/Fully-Connected-Network-Topology-diagram.png
Adapted from [Fully Connected Network Topology Diagram](https://www.conceptdraw.com/How-To-Guide/fully-connected-network-topology)
```
In HPC word, each computer in the network is called `compute node`.

- Definition of HPC + concept map
-->
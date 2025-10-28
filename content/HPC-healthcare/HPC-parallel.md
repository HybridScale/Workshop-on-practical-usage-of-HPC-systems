# Parallel and distributed computing


## Types of architectures

Today we have two basic types of parallel architectures - **share memory systems** and **distributed memory systems**. The combination of these two is called a hybrid systems and is the most common realization of modern HPC clusters. 


```{figure} ../img/dist-share-mem.png
Shared-memory vs. distributed-memory system arhitecture.
```

```{Callout} **Shared memory**
A type of system architecture (e.g. computer) that have a multiple physical processors having access to the common physical memory space. This means that all processors can read and write data to the same memory locations and exchange information.

**Advantages:** simpler to program, no need for explicit data transfers or sychronizationa among processors.

**Disadvantages:** can cause contention and scalability issues, processors compete for the memory access and bandwidth, cannot be easily scaled.
```

```{Callout} **Distributed memory**
A type of system architecture in which each processors or node has it own local memory and they communicate with each other through message passing. This means that each processor can access only its own memory space, and exchange information with other processors by sending and receiving messages.

**Advantages:** avoid contention and scalability, memory size does not limit the number of processors.

**Disadvantages:** more complicated to program, needs explicit data distribution and communication among the processors.
```

## Parallel programming models

### OpenMP

```{figure} ../img/OpenMP_logo.png
:width: 20%
:align: left
```

[OpenMP](https://www.openmp.org/) is a standard for programming shared memory systems. It is a directive-based programming model with a "lightweight" syntax that enables simple programming. The model uses the parallel fork-and-join model, i.e. the program is executed serially until it encounters a parallel region. Parallel regions are blocks of code that are executed simultaneously by all threads in a team.

```{figure} ../img/openmp-model.png
:height: 7cm
The fork-and-join parallel model. Figure taken from [https://docs.nersc.gov/development/programming-models/openmp/](https://docs.nersc.gov/development/programming-models/openmp/)
```

### MPI

Message Passing Interface (MPI) is a widely used standard for parallel computing on distributed memory systems in which multiple processors communicate with each other by exchanging messages. It allows efficient communication among processes running on different computing nodes in a computer cluster.

```{figure} ../img/mpi-basic.png
Basic MPI communication between two processors. Figure taken from [https://www.cs.mtsu.edu/~rbutler/courses/pp6330/www.llnl.gov/computing/tutorials/workshops/workshop/mpi/MAIN.html](https://www.cs.mtsu.edu/~rbutler/courses/pp6330/www.llnl.gov/computing/tutorials/workshops/workshop/mpi/MAIN.html).
```

The most popular implementations of the MPI standard are: [MPICH](https://www.mpich.org/), [OpenMPI](https://www.open-mpi.org/) and various vendor specific implementation based on those two.

### GPU programming models

[CUDA](https://docs.nvidia.com/cuda/cuda-c-programming-guide/index.html) and [ROCm](https://rocm.docs.amd.com/en/latest/) are parallel programming models for general purpose graphics cards (GPUs) developed by NVIDIA and AMD respectively. The model is based on the SIMT programming model (Single Instruction Multiple Threads), which means that a large number of threads execute the same single instruction asynchronously. As the GPUs are not independent processors, but accelerators or co-processors of the standard CPUs, the parts of the application code that are suitable for the GPU are offloaded while the rest of the code is executed on the CPU.

```{figure} ../img/gpu_acceleration.png
Heterogeneous programming model. Figure taken from [https://es.mathworks.com/help/gpucoder/gs/gpu-prog-paradigm.html](https://es.mathworks.com/help/gpucoder/gs/gpu-prog-paradigm.html)
```

---

## Job scheduling

Scheduling jobs and managing resources is one of the key components of HPC clusters that sets them apart from other types of computing systems. Since HPC clusters can have hundreds of users and compute nodes, it would be impossible to decide which users should use which resources without a queuing system. The specialized software called `scheduler` is responsible for deciding which user job is executed when on which resources (nodes).

```{figure} ../img/restaurant_queue_manager.png
:width: 100%
An illustration of the HPC job manager on the example of the restaurant. Figure taken from [https://epcced.github.io/hpc-intro/13-scheduler/index.html](https://epcced.github.io/hpc-intro/13-scheduler/index.html).
```

### Workflow

In a typical workflow, a user connects to the cluster's login node, where he/she describes (and prepares a job script file) how the jobs should be executed (the pipeline) and what resources are needed (number of processors, amount of memory, maximum execution time, etc.). Based on this information, the job scheduler places the job in the queue, where it waits until the requested resources are available. As soon as the resources are available, they are allocated and the job is executed on the allocated resources.

```{figure} ../img/batch_system.png
:width: 100%
Shematic of the batch scheduling system. Figure taken from [https://hpc-wiki.info/hpc/Scheduling_Basics](https://hpc-wiki.info/hpc/Scheduling_Basics)
```

The scheduler is responsible for all jobs of all users of the systems and tries to pack them as densely as possible onto the computing nodes in order to occupy the nodes as well as possible and minimize idle time.

```{figure} ../img/scheduler.png
:width: 100%
An example of how scheduler may distribute jobs onto nodes. Figure taken from [https://hpc-wiki.info/hpc/Scheduling_Basics](https://hpc-wiki.info/hpc/Scheduling_Basics)
```

---

## Measuring the performance

```{Callout} Measure of computer performance
**Floating-point operations per second (FLOPS)**: Number of floating-point artihmetic calculations that the processor can perform within a second.
```

| Name     | Unit     | Value |
|----------|----------|----------|
| megaFLOPS | MFLOPS |  10<sup>6</sup> |
| gitaFLOPS | GFLOPS |  10<sup>9</sup> |
| teraFLOPS | TFLOPS |  10<sup>12</sup> |
| petaFLOPS | PFLOPS |  10<sup>15</sup> |
| exaFLOPS  | EFLOPS |  10<sup>18</sup> |
| zettaFLOPS | ZFLOPS |  10<sup>21</sup> |


### Benchmarks

The main benchmark used for the Top500 list is the *High Performance LINPACK* ([HPL](https://www.netlib.org/benchmark/hpl/)) test and is based on a variant of *LU* factorization with row partial pivoting. The main critism is that it is not representative of many important applications.

A new benchmark, called the *High Performance Conjugate Gradients* ([HPCG](https://www.hpcg-benchmark.org)) is designed to exercise computational and data access pattern that more closely match a broader set of important applications.



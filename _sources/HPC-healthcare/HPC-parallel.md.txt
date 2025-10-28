# Parallel and distributed computing


## How to program parallel computers?

### [OpenMP](https://www.openmp.org/)

```{figure} ../img/OpenMP_logo.png
:width: 20%
:align: left
```

```{figure} ../img/openmp-model.png
:height: 7cm
The fork-and-join parallel model. Figure taken from [https://docs.nersc.gov/development/programming-models/openmp/](https://docs.nersc.gov/development/programming-models/openmp/)
```

### Message Passing Interface (MPI)

```{figure} ../img/mpi-basic.png
Basic MPI communication between two processors. Figure taken from [https://www.cs.mtsu.edu/~rbutler/courses/pp6330/www.llnl.gov/computing/tutorials/workshops/workshop/mpi/MAIN.html](https://www.cs.mtsu.edu/~rbutler/courses/pp6330/www.llnl.gov/computing/tutorials/workshops/workshop/mpi/MAIN.html).
```

The most popular implementations of the MPI standard are: [MPICH](https://www.mpich.org/), [OpenMPI](https://www.open-mpi.org/).

### GPU programming models

- [CUDA](https://docs.nvidia.com/cuda/cuda-c-programming-guide/index.html)
- [ROCm](https://rocm.docs.amd.com/en/latest/) 
  
```{figure} ../img/gpu_acceleration.png
Heterogeneous programming model. Figure taken from [https://es.mathworks.com/help/gpucoder/gs/gpu-prog-paradigm.html](https://es.mathworks.com/help/gpucoder/gs/gpu-prog-paradigm.html)
```

---

## Sharing cluster with others

Scheduling jobs and managing resources is one of the key components of HPC clusters that sets them apart from other types of computing systems. Since HPC clusters can have hundreds of users and compute nodes, it would be impossible to decide which users should use which resources without a queuing system. The specialized software called `scheduler` is responsible for deciding which user job is executed when on which resources (nodes).

```{figure} ../img/restaurant_queue_manager.png
:width: 100%
An illustration of the HPC job manager on the example of the restaurant. Figure taken from [https://epcced.github.io/hpc-intro/13-scheduler/index.html](https://epcced.github.io/hpc-intro/13-scheduler/index.html).
```

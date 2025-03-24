# Demonstration

<!--
## Hrvatski centar kompentencija za HPC

[HR HPC CC](https://www.hpc-cc.hr/) uspostavljen je u sklopu projekta EuroCC (2020 - 2022) kao dio mreže nacionalnih centara kompetencija za HPC u 33 države članice Zajedničkog poduzeća za europsko računarstvo visokih performansi (EuroHPC JU).

One-Stop-Shop za HPC
- podrška korisnicima u korištenju HPC resursa
- razvoj novih kompetencija iz HPC područja
- suradnja akademske zajednice i gospodarstva
- izgradnja europskog HPC ekosustava

HR HPC CC trenutno djeluje u sklopu projekta EuroCC 2 (2023 - 2025) čiji je cilj daljnje promicanje korištenja HPC-a na nacionalnoj razini identificiranjem relevantnih korisnika.

```{figure} ../img/eurocc-map.png

```
-->

In this demonstration, we present the basic step to access an HPC cluster, prepare a simple job and run it on compute nodes. The test system used is the [Supek](HPC-infra.md) supercomputer operated by the University Computing Centre of the University of Zagreb. In this session we will run [ChASE](https://github.com/ChASE-library/ChASE) (Chebyshev Accelerated Subsapce Eigensolver), a numerical library designed for solving large and complex eigenvalue problems on distributed computing systems.

The principles shown in this course apply to all clusters and supercomputers. However, each system may have its own software stack, hardware architecture and memory configuration.


## A typical cluster workflow

```{callout} The basic steps are the following:
1. **Authenticatio**n (this step is done only once, at the first login).
   1. Generating SSH keys.
   2. Copy public key to the remove server.
2. **Connect to** remote server using secure shell protocol (SSH).
3. **Copy** your **data** using secure copy (e.g. scp, rsync).
4. **Prepare a script** that describe how your application and data will be executed.
5. **Allocate resources** and submit your job using job and resource management system (e.g. SLURM, PBS).
6. Once the job is finished, **retrieve output** data.
```

```{figure} ../img/demo-run.png
An example of a typical HPC workflow.
```

---
### Generate SSH keys

The first step is to authenticate the computer that you will use to access the cluster. In this demonstration, we will show you how to generate SSH keys via command line. You acn find more options in the Supek [documentation](https://wiki.srce.hr/pages/viewpage.action?pageId=121966392) under 'Pristup klasteru Supek'.

<link rel="stylesheet" type="text/css" href="../../_static/asciinema-player.css" />
<body>
  <div id="sshkey-gen"></div>
  <script src="../../_static/asciinema-player.min.js"></script>
  <script>
    AsciinemaPlayer.create('../../extra/keygen.cast', document.getElementById('sshkey-gen'), {
      loop: false,
      fit: "width",
      terminalFontSize: 'medium',
      cols: 100,
      rows: 30,
      });
  </script>
</body>


---
### Upload public-key

After you have generated the key pairs, you must upload the public key (with the extension `*.pub`) to your account on *compute.srce.hr*. Once it is uploaded, it will be automaticaly copied to the `home` folder.
<body>
  <video width="640" height="360" controls>
    <source src="../../extra/add-key-to-supek.webm" type="video/webm">
    Your browser does not support the video tag.
  </video>
</body>

---
### Loggin to the cluster (login node)

To log in to Supek, connect to the GPU login node: *login-gpu.hpc.srce.hr* using `ssh` specifying your username and the path to your private key file.
As soon as you are logged, all interaction with the cluster will take place via the login node, as direct access to the compute nodes is not possible.

<link rel="stylesheet" type="text/css" href="../../_static/asciinema-player.css" />
<body>
  <div id="login-supek"></div>
  <script src="../../_static/asciinema-player.min.js"></script>
  <script>
    AsciinemaPlayer.create('../../extra/login-supek.cast', document.getElementById('login-supek'), {
      loop: false,
      fit: "width",
      terminalFontSize: 'medium',
      cols: 100,
      rows: 30,
      });
  </script>
</body>

---
### Copying files

Data transfer between a local computer and the cluster (i.e. login node) can be done either with graphical and command line  tools, as long as they support secure transfer protocols. Examples are [MobaXterm](https://mobaxterm.mobatek.net/) or [WinSCP](https://winscp.net/eng/download.php) for Windows or the command line tools `scp` and `rsync` for Linux.

An example of copying files from the local computer to the Supek using the command line tool scp.

<link rel="stylesheet" type="text/css" href="../../_static/asciinema-player.css" />
<body>
  <div id="copy-supek"></div>
  <script src="../../_static/asciinema-player.min.js"></script>
  <script>
    AsciinemaPlayer.create('../../extra/copy.cast', document.getElementById('copy-supek'), {
      loop: false,
      fit: "width",
      terminalFontSize: 'medium',
      cols: 100,
      rows: 30,
      });
  </script>
</body>

The example shows how the entire content of the folder `TiO2` is transferred from the local computer to the folder `DATA` on the Supek login node.

---
### Job queues

The compute nodes are organised in job queues depending on their intended use. There are nine [job queues](https://wiki.srce.hr/pages/viewpage.action?pageId=121966239) on Supek, each of which is optimised for certain types of jobs. 
The following commands should be executed from the Supek login node.

To list all available queues on the system, run:
```
qstat -Q
```

To display all running and pending (waiting) jobs in the `gpu` queueu, use the following command:

```
qstat -p gpu
```

Dispaly a complete list of nodes, including their utilisation and the jobs currently running on them:
```
pbsnodes -aSj
```


---
### Prepare working environment on the login node

In HPC clusters, several users often run different applications at the same time. Therefore, the applications in your working environment are not activated by default, but the users have to load it by themselves. This allows users to:
- Isolate their software environments for specific application/data requirements,
- Easily switcg between different application versions (e.g. a researcher may need both Python 2.7 and 3.8 for different applications),
- Manage dependencies effectively and minimise conflicts.

A widely used tool for managing pre-installed applications in HPC environments is `Modulefiles`. The primary command is `module`, and changes to the environment variables only apply to the current user session.

<link rel="stylesheet" type="text/css" href="../../_static/asciinema-player.css" />
<body>
  <div id="module-supek"></div>
  <script src="../../_static/asciinema-player.min.js"></script>
  <script>
    AsciinemaPlayer.create('../../extra/module.cast', document.getElementById('module-supek'), {
      loop: false,
      fit: "width",
      terminalFontSize: 'medium',
      cols: 100,
      rows: 30,
      });
  </script>
</body>

The `module list` command displays the loaded modules and shows which applications are active in your environment. In this case, only one module -- Python 3.10 -- is loaded, as it is required for the `asciinema` tool used to record the terminal session. 

To see all available modules installed on the system, use `module avail`. If you need to search for a specific module, `module spider pytorch` lists all available version fo the PyTorch framework -- in this example, four versions are pre-installed. Finally, to check what changes a particular module (e.g. `pytorch/2.0.0`) would make to your environment before you load it, you can view the details. 

The following video demonstrates the loading of several modules required to run our code.

<link rel="stylesheet" type="text/css" href="../../_static/asciinema-player.css" />
<body>
  <div id="load-modules-supek"></div>
  <script src="../../_static/asciinema-player.min.js"></script>
  <script>
    AsciinemaPlayer.create('../../extra/load-module.cast', document.getElementById('load-modules-supek'), {
      loop: false,
      fit: "width",
      terminalFontSize: 'medium',
      cols: 100,
      rows: 30,
      });
  </script>
</body>

---
### Prepare and submit job

Since our example application, the ChASE library, is not pre-installed on the system, we must first download it from the GitHub repository.
```
git clone https://github.com/ChASE-library/ChASE.git
```
and compile it using the `cmake` command (the commands are listed in the `gnu-activate.sh` files): 
```
cmake -B build-gnu-test \
 -DBUILD_WITH_EXAMPLES=ON \
 -DCHASE_OUTPUT=ON \
 -DCMAKE_CXX_COMPILER=CC \
 -DCMAKE_C_COMPILER=cc \
 -DCMAKE_Fortran_COMPILER=ftn \
 -DCMAKE_CUDA_COMPILER=nvcc -DCMAKE_CUDA_FLAGS="--allow-unsupported-compiler"

cmake --build $folder
```

The `cmake` searches for the reqired software dependencies and generates a `Makefile` (the first run of `cmake`). In the second run, it compiles (builds) the application. The resulting executable files are located in the `build-gnu-test` directory under  `examples` subfolder.

Once ChASE is compiled, we can create a simple script to define our job.

<link rel="stylesheet" type="text/css" href="../../_static/asciinema-player.css" />
<body>
  <div id="load-modules-supek"></div>
  <script src="../../_static/asciinema-player.min.js"></script>
  <script>
    AsciinemaPlayer.create('../../extra/load-modules.cast', document.getElementById('load-modules-supek'), {
      loop: false,
      fit: "width",
      terminalFontSize: 'medium',
      cols: 100,
      rows: 30,
      });
  </script>
</body>

In the script, we define the job parameters that the scheduler requires for resource allocation (lines beginning with the keyword `#PBS`). The remaining lines contain standard Linux commands to set up environment variables, load necessary modules and define paths. Finally, the ChASE executable is started with `mpiexec`, which executes the program in parallel on 4 parallel processes, each of which uses a separate GPU device.

<link rel="stylesheet" type="text/css" href="../../_static/asciinema-player.css" />
<body>
  <div id="prepare-run-chase"></div>
  <script src="../../_static/asciinema-player.min.js"></script>
  <script>
    AsciinemaPlayer.create('../../extra/prepare-chase.cast', document.getElementById('prepare-run-chase'), {
      loop: false,
      fit: "width",
      terminalFontSize: 'medium',
      cols: 100,
      rows: 30,
      });
  </script>
</body>

---
### Check job status

The status of the job can be checked woth the following command:

```
qstat -u testUser
```

This command only displays the active and pending jobs of the user with the username `testUser`.
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

In this demonstration, we will show you the basic principle of how to access an HPC cluster, prepare a simple job and execute it on the compute nodes. The test system is the supercomputer [Supek](HPC-infra.md) operated by the University of Zagreb, University Computing Centre. The test application running today is [ChASE](https://github.com/ChASE-library/ChASE), a Chebyshev Accelerated Subsapce Eigensolver for Dense Eigenproblems, a numerical library for solving large and complex eigenvalue problems on distributed computing systems.

The working principles demonstrated in this course are also applicable to all other clusters and supercomputers, but each may have its own software stack, hardware architecture and storage system.

user.


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

The first step is to authenticate the computer from which you plan to access the computer cluster. In this demo we will show to create SSH keys using command line. For more options check the Supek [documentation](https://wiki.srce.hr/pages/viewpage.action?pageId=121966392) (see 'Pristup klasteru Supek')

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

After the key pairs is created, the public key (the one with the extension `*.pub`) has to be uploaded to your account on *compute.srce.hr*. Once it is uploaded it will be automaticaly copied to the `home` folder
<body>
  <video width="640" height="360" controls>
    <source src="../../extra/add-key-to-supek.webm" type="video/webm">
    Your browser does not support the video tag.
  </video>
</body>

---
### Loggin to the cluster (login node)

To log into to the Supek, we have to connect to the GPU login node: *login-gpu.hpc.srce.hr* using `ssh` by providing your user name and the path to the private key file.
Once you are logged, all interaction with the cluster are done from the login node. There is no possibility to directly access any of the compute nodes.

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

To transfer data between local computer and the cluster (i.e. login node) can be done by using both graphical and command-ine transfer tools, as long as they support secure transfer protocol. For example [MobaXterm](https://mobaxterm.mobatek.net/) or [WinSCP](https://winscp.net/eng/download.php) for Windows and `scp` and `rsync` command line tools on Linux.

An example of copying files from the local computer to the Supek using scp command line tool.

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

The example show how to transfer the entire content of the folder `TiO2` from the local computer to the folder `DATA` at the Supek login node.

---
### Job queues

The compute nodes are grouped into job queues, based on the specific use. For example on Supek are defined 9 [job queues](https://wiki.srce.hr/pages/viewpage.action?pageId=121966239) each tailored for a specific types of jobs. 
The next command are run on the login node of the Supek.

To list all available queues on the system run:
```
qstat -Q
```

To list all the jobs that are currently running in the `gpu` queueu or are in the pending (waiting) can be inspected by running:

```
qstat -p gpu
```

Print the full list of nodes with their loads and the jobs currently running on them.
```
pbsnodes -aSj
```


---
### Prepare working environment on the login node

In HPC clusters, several users often work simultaneously with different applications. Therefore, the applications in your current working environment are not activated by default. The reason for this is that users can isolate their software environments for their specific needs, easily switch between different versions of the same application (e.g. a researcher needs both Python 2.7 and 3.8 for different projects) and support application dependency management and the reduction of possible collisions.

Nowadays, one of the most common tools of the pre-installed appliation management in the HPC envorionment is called `Modulefiles`. The basic command is `module` and all changes on the environment variables are applicable only in the current session.

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

The command `module list` shows the currently loaded modules, i.e. the applications loaded in my environment. There is only one module, Python version 3.10, which was needed for the little tool called `asciinema`, which allowed me to record my terminal window. The command `module avail` shows all available modules that are installed in the system. Then we use `module spider` to search for a specific module called `pytorch`, which lists 4 different versions of the pytorch framework that are pre-installed on the system. Finally, we can check what the specific module (`pytorch/2.0.0`) would do in our environment if it were loaded. 

In the followin video is shown the loading of a several module required to execute our code.

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

The ChASE library is first cloned from the GitHub
```
git clone https://github.com/ChASE-library/ChASE.git
```
and then compiled using `cmake` command (the commands are packed in the `gnu-activate.sh` files): 
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

which will find the reqired dependencies for our program and prepare `Makefile` (first call to `cmake`) and then compile the application (second `cmake`). The executables are located in the `build-gnu-test` files under subfolder `examples`

Now, the ChASE is compiled, we can create a simple script file describing our job.

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

In the script we define the job parameters that the scheduler requires for the allocation of resources (lines beginning with the keyword `#PBS`). The remaining lines are standard Linux commands that prepare environment variables, load modules, define paths, etc. Finally, the executable file of ChASE is started with the program `mpiexec`, which starts our executable file in parallel in 4 parallel processes, each running on a GPU device.

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



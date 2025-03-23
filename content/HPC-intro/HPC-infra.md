# Available infrastructures

Supercomputers are substantial and costly machines utilized across academia, industry, business, and the military, playing an increasingly strategic role. Currently, a fierce competition exists between the USA and China in terms of the number of installed HPC systems and their computational power, with Europe trailing behind these two leaders.

The list of the world's fastest supercomputers can be found in the renowned **[Top500](https://www.top500.org/lists/top500/2024/11/)** list, which is updated twice a year (in June and November). This list provides comprehensive technical details and statistics for the available systems, encompassing computing systems from both academic and private sectors. The ranking is based on the achieved performance (measured in PFLOPS) using the **[LINPACK Benchmark](https://www.netlib.org/benchmark/hpl/)** for distributed-memory LU factorization with partial pivoting in double-precision arithmetic.

An additional metric for ranking HPC systems is the **[High-Performance Conjugate Gradients (HPCG)](https://www.hpcg-benchmark.org/)** benchmark. This benchmark is designed to evaluate computational and data access patterns that closely align with a wide range of significant applications, assessing performance in areas that the LINPACK benchmark may not fully address.

```{figure} ../img/top500.png
Supercomputers' performance development since the early 1990s [Top500, [June 2023](https://www.top500.org/statistics/perfdevel/)]
```

## Fairsharing access policy

The majority of the supercomputers apply the fairsharing policy. It is the resource allocation policy or mechanism that aims to distribute computing resources fairly among multiple users or user groups. The objective of a fairshare policy is to ensure that each user or group receives a proportional share of the supercomputer's resources, such as CPU time, memory, or storage capacity, based on their needs and priorities.

```{callout} No exlusive allocation of resources!
Individual users or user groups do not have exclusive access to specific resources like CPUs, GPUs, or memory. Instead, they are allocated computational time on these resources, ensuring that the physical resources are fairly shared with other users of the computing system.
```
---

## Local HPC systems (EDIH AI4Health.CRO)

A local GPU cluster **[ORTHUS](https://hybridscale.github.io/orthus/index)** located at the Ruđer Bošković Institute, in Zagreb. The systems comprises of a frontend and a compute node, armed with 2 Intel Xeon Gold processors (providing a total of 48 computing cores), 4 NVIDIA A100 GPUs, 512 GB of main memory, and 60TB of storage. The system operates on the CentOS7 operating system and utilizes the SGE queuing system.

Orhus primarily serves as a local platform for tasks such as code development, testing, proof-of-concept endeavors, and conducting smaller-scale analyses and simulations.

```{challenge} How to access?
Access to the cluster is limited to the RBI network for security purposes and can be achieved through two methods:
- Remote connection from within the RBI network.
- Remote connection from outside the RBI network via a VPN connection.

To request access, please send an email to [orthus-info@irb.hr](mailto:orthus-info@irb.hr)
```
---

## HPC systems in Croatia

### BURA (Univ. of Rijeka)

The first supercomputer in Croatia was [BURA](https://cnrm.uniri.hr/bura/) located at the Centre for Advanced Computing and Modelling (CNRM) at the University of Rijeka. The application of Bura is for advanced modeling and optimization in the fields of biotechnology, biomedicine, nanoscience, physics and other branches of science and industry.

The supercomputer is a hybrid computing system consisting of three main parts:
- **Cluster**: the multicomputer system consisting of 288 compute nodes each equipped with two Intel Xeon E5 processors (24 cores per node). A total of 6912 processor cores and 18 TB of (distributed) main memory.
- **GPGPU**: 4 heterogeneous nodes each with two NVIDIA Tesla K40 general purpose GPUs.
- **SMP**: 2 multiprocessor nodes with a large amount of shared memory (6 TB main memory and 245 TB of local storage).

```{figure} ../img/CNRM_Bura.png
Taken from [Cente for Advanced Computing and Modelling (CNRM)](http://iuri.uniri.hr/center/center-for-advanced-computing-and-modelling-cnrm/)
```

The system has a wide range of pre-installed open-source and proprietary software. You can access the comprehensive list of these software packages [here](https://cnrm.uniri.hr/software/).

```{challenge} Some facts
- Acquired in 2015.
- #441 at TOP500 (287 TFLOPS) at the time of installation
- 288 compute nodes
- 6912 processing cores
- 17 TB main memory
- 95 TB storage​
```

```{challenge} How to access?
The Bura supercomputer is primarly intended for academic use, but access can also be granted to industry/SME. The request can be made by filling in the online [form](https://cnrm.uniri.hr/contact/).

Typically, an initial **trial period of up to one month** is provided, after which the industry or SME is expected to cover resource usage costs based on the core-hours. The total resource allocation (and price) are negotiate individually per-user with the system provider (CNRM - UNIRI).
```
---

### SUPEK (University Computing Centre, Univ. of Zagreb - SRCE)

**[Supek](https://wiki.srce.hr/display/NR/Supek)** stands as the largest computer cluster in Croatia and the first to achieve a performance exceeding 1 PTFLOPS (1.25 PFLOPS). The system was acquired in 2022 as part of the HR-ZOO project, which received co-financing from the European Union.

Operated by the University Computing Centre ([SRCE](https://www.srce.unizg.hr/)) at the University of Zagreb, Supek is made accessible to the entire Croatian research and academic community, spanning across all research disciplines.

```{figure} ../img/supek.png
The largest supercomputer in Croatia - Supek. Picture taken from [Napredno računanje - Supek](https://wiki.srce.hr/display/NR/Supek)
```

```{challenge} Technical info
- HPE Cray EX
- 8384 compute cores
- 81 graphic processors
- 32 TB main memory
- 52 CPU-only compute nodes
- 20 GPU compute nodes (NVIDIA A100)
- 2 login nodes

The full documentation of the architecture of Supek can be found [here](https://wiki.srce.hr/display/NR/Arhitektura+Supeka).
```

```{challenge} How to access?
The access to Supek is possible for:
- Research projects financed from the public sources.
- Preparation of final, bachelor's, specialist, and doctoral theses at public higher education institutions and public scientific institutes.

More on the access rules can be found [here](https://wiki.srce.hr/display/NR/Pristup).
```
The application proces is done through the [online application](https://computing.srce.hr/ui/prijava) form. 

```{callout} Access for industry
**Currently, there is no possiblity for the business sector to access this resource!**
```

---

## HPC systems in Europe

In 2018, the European High-Performance Computing Joint Undertaking ([EuroHPC JU](https://eurohpc-ju.europa.eu/index_en)) was established as a collaborative initiative involving the EU, European countries, and private partners. The primary objective is to build a world-class supercomputing ecosystem in Europe, with a central focus on creating a pan-European supercomputing infrastructure. This infrastructure aims to support research and innovation endeavors, extending its benefits not only to academia but also to the industry, SMEs, and the business sector.

### EuroHPC JU supercomputers

Currently there are [10 supercomputers](https://eurohpc-ju.europa.eu/supercomputers/our-supercomputers_en), 3 pre-exascale supercomputers and 5 petascale supercomputers, and one exascale (JUPITER).

<!--```{figure} ../img/eurohpc-computers-location.png
Site locations of EuroHPC JU supercomputer locations. Figure taken from [EuroHPC Systems Report - September 2021](https://eurohpc-ju.europa.eu/document/download/4fd55c3d-8051-4820-8ec8-555c9dbe64a7_en?filename=EuroHPC%20Systems%20Report-Sep2021.pdf).
```-->

```{figure} ../img/eurohpc-computers.png
Site locations of EuroHPC JU supercomputer locations. Figure taken from [EuroHPC Systems Report - April 2023][(https://eurohpc-ju.europa.eu/document/download/4fd55c3d-8051-4820-8ec8-555c9dbe64a7_en?filename=EuroHPC%20Systems%20Report-Sep2021.pdf](https://eurohpc-ju.europa.eu/document/download/f43c0ad2-d486-42e7-a543-59bd8314b269_en?filename=ED-8984_CORDIS_LotB_PiP%20on%20European%20supercomputing_2nd%20ed_Brochure_LR%20ac.pdf).
```

- Exascale (Europe's first exascale)
  - [JUPITER](https://www.fz-juelich.de/en/ias/jsc/jupiter) (arrival in 2024?), [Forschungszentrum Juelich](https://www.fz-juelich.de/en), Juelich, Germany
- Pre-exascale
  - [LUMI](https://www.lumi-supercomputer.eu/lumi_supercomputer/), [CSC](https://www.csc.fi/) - IT Centre for Science, Kajaani, Finland
  - [Leonardo](https://leonardo-supercomputer.cineca.eu/), [CINECA](https://www.cineca.it/en/), Bologna, Italy
  - [MareNostrum5](https://www.bsc.es/marenostrum/marenostrum-5), Barcelon Supercomputing Centre ([BSC](https://www.bsc.es/)) Barcelona, Spain
- Petascale
  - Discoverer
  - [Vega](https://www.izum.si/en/hpc-en/), [IZUM](https://www.izum.si/en/home/), Maribor, Slovenia
  - [MeluXina](https://luxembourg.public.lu/en/invest/innovation/meluxina-superordinateur.html), [LuxProvide](https://luxprovide.lu/), Bissen, Luxembourg
  - [Karolina](https://www.it4i.cz/en/infrastructure/karolina), [IT4Innovations](https://www.it4i.cz/en) National Supercomputing Center, Ostrava, Czech Republic
  - [Discoverer](https://sofiatech.bg/en/petascale-supercomputer/), [Sofia Tech Park](https://sofiatech.bg/en/), Sofia, Bulgaria
  - [Deucalion](https://macc.fccn.pt/resources#deucalion), [MACC](https://macc.fccn.pt/), Guimaraes, Portugal

The complete technical information on all EuroHPC JU Supercomputer systems (as of September 2012) can be found [here](https://prace-ri.eu/wp-content/uploads/EuroHPC-Systems-Report-Sep_2021.pdf).

### Access
```{challenge} Free access to EuroHPC supercomputers
**Who is eligible?**
- Academic and research institutions (public and private)
- Public sector organisations
- Industrial enterprises and SMEs

**Which type of access exists?**
- Extreme Scale
- Regular
- Benchmark
- Development
- Academic Fast Track
- Industry Fast Track

More information on the types of access can be found [here](https://www.hpc-cc.hr/EuroHPC_resursi)(in Croatian)
```

```{figure} ../img/EuroHPC_access_modes.png
Types of access to EuroHPC supercomputers. Table taken from [Hrvatski centar kompetencija za HPC - EuroHPC resursi](https://www.hpc-cc.hr/EuroHPC_resursi).
```

*New type of EuroHPC JU Access [call](https://eurohpc-ju.europa.eu/eurohpc-ju-access-call-ai-and-data-intensive-applications_en) for AI and Data-Intensive Applications.*


```{callout} What are the conditions for access?
Access if free of charge. Participation conditions depend on the specific access call that a research group has applied to. In general, users of EuroHPC systems commit to:
- Acknowledge the use of the resources in their related publications
- Contribute to dissemination events upon request
- Produce and submit a report after completition of a resource allocation
- Applicants allow PRACE and EuroHPC JU to publish the Final Report of the awarded projects as of one year from the end date of the allocation period
- The applicant commits to not use the project results for military purposes 
```
### How to apply?

To apply for access to the EuroHPC JU supercomputers, you can submit proposals through the [Open Calls](https://eurohpc-ju.europa.eu/access-our-supercomputers/eurohpc-access-calls_en).
The Development and Benchmark calls are continuously open, with deadlines set for the first day of each month, while the Regular access calls have two application deadlines per year.

Detailed information on Access Policy can be found [here](https://eurohpc-ju.europa.eu/access-our-supercomputers/access-policy-and-faq_en).

An examples of the EuroHPC-JU Benchmark [call](https://eurohpc-ju.europa.eu/eurohpc-ju-call-proposals-benchmark-access_en) will all needed information and the total amount of resources available per each EuroHPC-JU supercomputer.

---

## Private HPC providers

### Arctur Ltd.

[Arctur](https://arctur.si/) is a private company whose main focuse is on research and innovations for business and running the HPC infrastructure and Data Centre. It is the only private supercomputer service provider in Central Eastern Europe.

The company provider HPC & Cloud resources called [Arctur-2](https://arctur.si/hpc-and-cloud/) which is delivered in the form of the Cloud service (cluster-in-the-cloud)

```{figure} ../img/Arctur-hpc.png
Arctur supercomputer. Picture taken from [HPCwire](https://www.hpcwire.com/off-the-wire/arctur-offers-access-hpc-infrastructure-hpc-challenge/)
```

```{challenge} How to access?
Remote access to the cluster. Two types of access modes:
- [Web-store](https://www.arctur.si/arctur-web-store/hpc/) - "renting" nodes (not CPU-time), price based on min. 100 node-hours
- Project oriented - joint project proposal
```

```{callout} 
- Based on the Cloud infrastructure
- Dual Ethernet inteconnection (not for high-demanding communication applications)
- preinstalled SLURM (in the case multiple nodes are used)
- All data encrypted
- Additional storage has to be paid (1 TB)
```

---

```{challenge} You need help?

As the EDIH [AI4Health.Cro](https://ai4healthcro.eu/), we are here to assist you in defining your requirements, identifying the most suitable HPC resources for your needs, and guiding you through the process of application for accessing the HPC resources.
```
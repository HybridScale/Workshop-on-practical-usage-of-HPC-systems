# Introduction to High-Performance Computing

---

## 1. From Room-Sized Machines to Life-Saving Simulations

Before diving into what *High-Performance Computing (HPC)* means today, let’s take a quick trip through time — from the machines that filled entire rooms to the systems that help us model the human brain, predict pandemics, and design new cancer drugs.

> 💬 **Speaker note:**  
> Open with a relatable statement:  
> “Every medical CT scanner, every AI diagnostic model, every virtual drug screen — all of them trace their roots to computing power that started growing 80 years ago.”

---

### 1940–1960s: The First Supercomputers  
**The birth of electronic computing**

The first “supercomputers” emerged during World War II. They weren’t built for medicine, but for **codebreaking, ballistics, and physics** — yet they laid the foundation for every modern medical simulation.

- 🖥️ **ENIAC** (1945) — the first electronic general-purpose computer, built for U.S. Army ballistics.  
- These early machines were massive — **the size of an operating room**, consuming as much electricity as a hospital wing.  
- Their mission: **calculate faster than any human could**.

```{figure} ../img/eniac.jpg
ENIAC (1945) — one of the first electronic supercomputers, programmed manually with cables and switches. Figure taken from [Wikipedia](https://hr.wikipedia.org/wiki/ENIAC).
```

<!-- > 💬 **Speaker note:**  
> “Just like medicine once relied on mechanical thermometers and hand-drawn charts, early science relied on machines like ENIAC to crunch equations that humans couldn’t handle.” -->

---

### 1970–1990: The Cray Era  
**When speed became a race**

In the 1970s, speed became the focus.  
Supercomputers like the **Cray-1** used *vector processors* to perform thousands of operations at once — a breakthrough that inspired modern GPUs (used in AI today).

```{figure} ../img/Cray-1.jpg  
“Cray-1 (1976) — elegant design and groundbreaking parallelism.”  
*(Original: [Wikipedia – Cray-1](https://en.wikipedia.org/wiki/Cray-1))*
```

<!-- > 💬 **Speaker note:**  
> “By the 1980s, HPC was no longer a military toy. It became the scientist’s microscope — used in chemistry, fluid dynamics, and even early biological modeling.”-->

---

### 1990–2010: The Cluster Era  
**From super-machines to super-teams of computers**

Scientists realized that connecting *many smaller computers* could outperform one massive one — the birth of **clusters**.

- 1994: NASA engineers built the first *Beowulf Cluster* using standard PCs and Ethernet cables.  
- This democratized HPC — universities could now build their own “mini supercomputers.”

```{figure} ../img/Beowolf2-300x174.jpg
Photo of a Beowolf Cluster. Figure taken from [https://memim.com/beowulf-cluster.html](https://memim.com/beowulf-cluster.html).
```

<!-- > 💬 **Speaker note:**  
> “It’s like assembling a hospital network — many units working together, rather than one massive central building.”-->

---

### 2010–Present: The GPU & Hybrid Era  
**From physics to AI and medicine**

Today’s supercomputers combine **traditional CPUs** with **GPUs and accelerators** — the same hardware used for medical AI, radiology, and genomics.  
Instead of a few super-fast processors, modern systems have **thousands of smaller ones working together**.

```{figure} ../img/supek-gpu-server.png
Modern HPC combines CPUs and GPUs for AI, simulations, and data analytics.
```

<!-- > 💬 **Speaker note:**  
> “We no longer chase higher clock speeds. Instead, we work smarter — splitting the work among many processors, just as hospital teams share complex cases.” -->

---

## 2. What Is HPC — and Why It Matters to You

So what exactly *is* HPC?

**High-Performance Computing (HPC)** means using **many powerful computers at once** to solve problems that are **too big, too detailed, or too urgent** for a single machine.

It’s the **engine behind modern data-driven medicine** — where algorithms, images, and molecules meet computation.

What is High-Performance Computing - [YouTube](https://www.youtube.com/watch?v=IniYMq2bJRI&t=1s) (Croatian).

<!--🖼️ **Suggested visual:**  
Modern infographic showing a cluster → cloud of healthcare icons (DNA, brain scan, molecule, hospital).  
*(Title: “How HPC powers modern medicine.”)*-->

<!-- >💬 **Speaker note:**  
> “Think of HPC as a hospital for data — thousands of processors working together to diagnose, simulate, and predict faster than any workstation could.”-->

---

### HPC in Everyday Healthcare Research

Here’s how HPC touches your field, even if you don’t see it directly:

| Application | HPC’s Role |
|--------------|------------|
| **Radiology AI** | Train deep neural networks on thousands of MRI/CT scans. |
| **Drug discovery** | Simulate how molecules bind to proteins. |
| **Genomics** | Process hundreds of patient genomes in parallel. |
| **Epidemiology** | Model virus spread and hospital resource needs. |
| **Surgery planning** | Run 3D simulations of patient anatomy. |

<!-- > 💬 **Speaker note:**  
> “Behind every AI paper in *The Lancet* or *Nature Medicine*, there’s almost always an HPC system doing the heavy lifting.”-->

---

## 3. Why Do We Need HPC?  

Most modern medical and pharmaceutical challenges are **too large for desktop computers**:

- A single CT scan can produce **hundreds of megabytes** of data.  
- One genome = **100 GB** of raw data.  
- A deep learning model might require **weeks of computation** without HPC.

🖼️ **Suggested visual:**  
Graphic: “Laptop vs. HPC Cluster” — same task (e.g., drug screening) shown taking weeks vs. hours.

---

### The Grand Challenges (and Opportunities)

The U.S. National Science Foundation once defined “**Grand Challenges**” — problems only solvable with HPC.  
Many now directly relate to healthcare and life sciences:

- Cancer detection and therapy  
- Drug design and molecular simulation  
- Climate and disease modeling  
- AI and deep learning  
- Understanding biological systems  

<!-- > 💬 **Speaker note:**  
> “We often talk about grand challenges in medicine — curing cancer, predicting pandemics, understanding aging. HPC gives us the computational microscope to tackle them.”-->

---

### In One Sentence:

> 🧠 **HPC allows us to ask bigger questions — and get answers faster.**

``{callout} You can:
- Solve **bigger problems in the same time**, or  
- Solve **the same problems in less time**.

<!-- 🖼️ **Suggested visual:**  
Simple two-column infographic:  
_Left: “1 patient, 1 week”_ → Right: “1000 patients, 1 week”_  
(Caption: “Parallel computing accelerates discovery.”)-->

---

### Reflection

```{challenge} Where could HPC help you?
Think of a task in your daily work — an analysis, simulation, or AI model — that you *wish* could run faster or on more data.  
Would HPC make it possible?


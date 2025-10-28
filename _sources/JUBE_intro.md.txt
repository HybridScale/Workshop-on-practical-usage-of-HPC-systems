Introduction to JUBE
====================

```{objectives}
- get an basic overview of JUBE benchmark framework
- compare benchmark and workpackage concept
```

The JUBE benchmarking environment provides a script-based framework for easily creating benchmark sets of the same or 
different applications. For each individual benchmark set, a configured parameter range is created and an analysis of 
these tests is provided after execution. For this purpose, the output data of the applications are analysed by automatic 
pre- and post-processing scripts that collect information and store it in a condensed form for manual evaluation. 
It is actively being developed by the Jülich Supercomputing Centre of Forschungszentrum Jülich, Germany.

## How it works
Once excuted JUBE creates a directory for the benchmark run (relative to the position of the input file), which is created 
if it does not already exist. This directory is important because it is the main interface for communicating with your benchmark. 
It creates the log files `run.log` for many useful debugging outputs.

JUBE runs the benchmark for each configured parameter independently in a new environment called a workpackage. In the files
`configuration.xml`and `workpackages.xml`, it stores benchmark configurations and extended workpackage parameters.

![Benchmark layout](img/benchmark_layout.png)

### Benchmark output
Runing benchmark produces next output on command line:
<link rel="stylesheet" type="text/css" href="../_static/asciinema-player.css" />
<body>
  <div id="demo"></div>
  ...
  <script src="../_static/asciinema-player.min.js"></script>
  <script>
    AsciinemaPlayer.create('../extra/jube_hello_world.cast', document.getElementById('demo'), {
      loop: false,
      fit: "width",
      terminalFontSize: 'big',
      cols: 55,
      rows: 30,
      markers: [8.85],
      pauseOnMarkers: true
      });
  </script>
</body>

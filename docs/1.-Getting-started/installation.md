---
title: Installation
author: "Paweł Obrępalski"
date: "July 4, 2017"
output: html_document
---

# Installation
## Downloading files
```bash
git clone https://github.com/CFD-GO/TCLB.git
cd TCLB
```

## Dependencies

In order to use TCLB solver, the following tools are required:

* [R](https://www.r-project.org/)
* packages for R: [optparse](https://cran.r-project.org/package=optparse), [numbers](https://cran.r-project.org/package=numbers),  [template](https://github.com/llaniewski/rtemplate), [gvector](https://github.com/llaniewski/gvector),  [polyAlgebra](https://github.com/llaniewski/polyAlgebra)
* [nVidia CUDA](https://developer.nvidia.com/cuda-zone) (if you want to use GPU)
* [python](https://www.python.org/)
* [numpy](http://www.numpy.org/) (if you want to use the integrated python interpreter)
* [python](https://www.python.org/), [python](http://www.sympy.org/) 
* [rPython](https://cran.r-project.org/package=rPython) (if you want to develop a model using python in place or R)
* [MPI](https://en.wikipedia.org/wiki/Message_Passing_Interface) (e.g. [OpenMPI](http://www.open-mpi.org

Most of them can be installed using the script provided within the code(tools/install.sh):

```bash
sudo tools/install.sh cuda 6.5-14
sudo tools/install.sh r
sudo tools/install.sh openmpi
     tools/install.sh rdep
sudo tools/install.sh python-dev
     tools/install.sh rpython
```

## Compilation

After installing all required dependencies, the code is ready to be compiled. In order to do so:
```bash
make configure
./configure
make -j 10 d2q9
```
Notes: `-j 10` is used to speed up the compilation process, by running multiple threads. `d2q9` is the name of the model, this solver comes with multiple models(TODO:link), which can be compiled(and used) by substituting `d2q9` for desired model name(e.g. `d3q27`).

### Configuration options

Option                | Effect
-------------         | ---------------------------------------------------------
`--enable-graphics`   | Enables the (TODO:okno podglądu).
`--disable-double`    | Switches to single(float) precision.
`--disable-cuda`      | Disables CUDA, thus compiling the code for CPU.
`--with-nlopt`        | Compilation with NLopt library for optimization.
`--with-python`       | Compilation with enabled Python integration(TODO:do użycia w XML).
`--with-r`            | Compilation with enabled R integration(TODO:do użycia w XML).

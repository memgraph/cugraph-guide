# cugraph-guide

## Example

```
TODO(gitbuda): Add basic C++ example of how to run PageRank once it's done.
```

## Installation

TODO(gitbuda): How to install proper version of Cuda (cuGraph requires 11+).
TODO(gitbuda): Some notes on how to install/compile cuGraph.

Keep versiong of both conda cugraph and cudatoolkit aligned between .py and .so
modules because they all use one Cuda library. E.g. if Cuda 11.5 is used to
compile .so file, install the same version inside conda environment.

## Graph Representations

### https://people.sc.fsu.edu/~jburkardt/data/mm/mm.html

```
cugraph::test::read_graph_from_matrix_market_file
```

### Explain https://en.wikipedia.org/wiki/Sparse_matrix

TODO: Explain COO, CSR, CRS

## NVIDIA Abstractions

### Nomenclature

`h_rows` probably means host (CPU) rows.
`d_rows` probably means device (GPU) rows.
`uvector` probably means uninitialized vector.
`_sg` probably means single GPU.
`_mg` probably means multi GPU.

### RMM - RAPIDS Memory Manager

Helps in dealing with device (GPU) and host (CPU) memory allocation. Since
`RMM` is an object dealing with the actual data, it is used to deal with the
device data from the host program.

### RAFT - RAPIDS Analytics Framework Toolkit

Helps with executing analytics on top of `RMM` data structures but also dealing
with the actual data, e.g., copying data from host to device and the other way
around.

### Thrust - RAPIDS c++::std

Helps with running C++ standard library like tasks on GPU.

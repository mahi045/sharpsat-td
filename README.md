# Tree-Decomposition of SharpSAT-TD
This is a modified implementation to compute cut of a formula using tree decomposition. It is used in [MinLB](https://www.cambridge.org/core/journals/theory-and-practice-of-logic-programming/article/on-lower-bounding-minimal-model-count/8A0A50842E7F625DA60C24A28050434D).


# Compiling

The external dependencies needed are the [GMP library](https://gmplib.org/), the [MPFR library](https://www.mpfr.org/), and [CMAKE](https://cmake.org/).

To compile and link dynamically use

``./setupdev.sh``

To compile and link statically use

``./setupdev.sh static``


The binaries sharpSAT and flow_cutter_pace17 will be copied to the [bin/](https://github.com/Laakeri/sharpsat-td/tree/main/bin) directory.

## Flags

- `-decot` - the number of seconds to run flowcutter to find a tree decomposition. Required. Recommended value 60-600 if running with a total time budjet of 1800-3600 seconds.
- `-tpmdir` - the directory to store temporary files for running flowcutter. Required.
- `-decow` - the weight of the tree decomposition in the decision heuristic. Recommended value >1 if the heuristic should care about the tree decomposition.
- `-cs` - limit of the cache size. If the memory upper bound is X megabytes, then the value here should be around x/2-500.
- `-WE` - enable weighted model counting with arbitrary precision.
- `-WD` - enable weighted model counting with double precision.
- `-prec` - the number of digits in output of weighted model counting. Does not affect the internal precision.
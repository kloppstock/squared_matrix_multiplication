#Documentation

##General Information

This project is meant compare the speed of different implementations of matrix multiplications (double precission).

All versions in the 4 programming languages (FORTRAN, C (with OpenMP and pthread; selected via compiler flag), Java and Haskell) are multithreaded. The Java version additionally benchmarks the single core performance for reference. Haskell is more or less just a proof of concept and is not really comparable to the other languages.

##Algorithm

![Algorithm](/Diagramm/Nassi-Shneidermann-Diagramm.png)

##Benchmarking system

All implementations were benchmarked on an Intel Core i5 6200U. 

CPU-features:
 * 2 Cores (with 2 Threads each)
 * 2.3 GHz base frequency
 * 2 FPU operations per clock
 * AVX 2 (256 Bit)
 * Fused Multiply Add
 
The resulting theoretical Floating Point Peak Performance (FPPP) is calculated as follows:

```2 Cores * 2.3 GHz * 2 FPU operations / clock * (256 Bit AVX / 64 Bit Double Precision) * 2 = 73.6 GFLOPS```

##Benchmarks

For detailed performance graphs please see [benchmarks/README.md](/benchmarks/README.md).

A performance table is also available at [benchmarks/benchmarks.csv](/benchmarks/benchmarks.csv).

The size - performance table can be found at [benchmarks/performance.csv](/benchmarks/performance.csv).

##Results

As expected, the C version perfomed best, shortly followed by fortran and later java. Haskell's performance was far from the other implementations. Fortran's performance leveld at around 1.18 GFLPOS, whereas Java declined with the matrix size from about 2.6 GFLOPS. The C version also appeared to decline (from around 4.7 GFLOPS) but doesn't showed any clear pattern.

The highest achieved performance was the C version with 4.744 GFLOPS at a size of 200 x 200, which is about 6.44% of the maximal FPPP of the CPU.

##Contributers

FORTRAN: Aaron Bulmahn [arbu](https://github.com/arbu) <br>
C: Jonas Schenke [kloppstock](https://github.com/kloppstock) <br>
Java: Matthias Nickel [matzeni07](https://github.com/matzeni07) <br>
Haskell: Sebastian Benner [De-Narm](https://github.com/De-Narm)

This project is hosted on [Github](https://github.com/kloppstock/squared_matrix_multiplication).

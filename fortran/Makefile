F90=gfortran
FFLAGS=-O3 -march=native

PYTHON=python

TARGET=matmul matmul_openmp
SOURCE=$(TARGET:=.f90)

all: $(TARGET)

%_openmp: %.f90
	$(F90) $(FFLAGS) -fopenmp -o $@ $<

%: %.f90
	$(F90) $(FFLAGS) -o $@ $<

benchmark: all
	$(PYTHON) benchmark.py

clean:
	rm -f $(TARGET) results.csv matrix.mod

.PHONY: clean all benchmark

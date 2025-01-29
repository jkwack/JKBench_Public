#CC=icx
CC=mpicc

SDIR=./
SRC=${SDIR}/Comp_GeoSeries_omp.c

EXE_DP=Comp_GeoSeries_omp_${CC}_DP
#EXE_SP=Comp_GeoSeries_omp_${CC}_SP
CFLAGS=-g -O2 -fiopenmp -fopenmp-targets=spir64 -D__STRICT_ANSI__
#CFLAGS=-fiopenmp -fopenmp-targets=spir64 -cpp
LDFLAGS=

EXES=$(EXE_DP) $(EXE_SP)

all: $(EXES)

$(EXE_DP): $(SRC)
	$(CC) $(CFLAGS) $^ -o $@ $(LDFLAGS)
	rm -rf *.o *.mod *.dSYM


$(EXE_SP): $(SRC)
	$(CC) $(CFLAGS) -DSP $^ -o $@ $(LDFLAGS)
	rm -rf *.o *.mod *.dSYM


.SUFFIXES:
.SUFFIXES: .c .o .f90 .cu .cpp .cuf
.PHONY: clean
clean:
	rm -rf *.o *.mod $(EXES) *.dSYM



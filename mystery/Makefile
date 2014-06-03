CC = icc
F90 = ifort
MPICC = mpicc
MPIF90 = mpif90

OMP_FLAGS = -openmp
OPT_FLAGS = -g
OBJS = darts-segfault darts-hang darts-wrong

all: ${OBJS}

darts-segfault: darts-segfault.o lcgenerator.h
	${MPICC} ${OPT_FLAGS} -o darts-segfault darts-segfault.o

darts-hang: darts-hang.o lcgenerator.h
	${MPICC} ${OPT_FLAGS} -o darts-hang darts-hang.o

darts-wrong: darts-wrong.o lcgenerator.h
	${MPICC} ${OPT_FLAGS} -o darts-wrong ${OMP_FLAGS} darts-wrong.o

darts-segfault.o: darts-segfault.c
	${MPICC} ${OPT_FLAGS} -c darts-segfault.c

darts-hang.o: darts-hang.c
	${MPICC} ${OPT_FLAGS} -c darts-hang.c

darts-wrong.o: darts-wrong.c
	${MPICC} ${OPT_FLAGS} ${OMP_FLAGS} -c darts-wrong.c

clean:
	rm -rf *.o ${OBJS}

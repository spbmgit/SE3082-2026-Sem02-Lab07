CC = mpicc
NP = 4

PROGRAMS = sum_bcast sum_scatter sum_gather sum_reduce sum_allreduce sum_scan

all: $(PROGRAMS)

sum_bcast: ../Exercise01/sum_bcast.c
	$(CC) -o sum_bcast ../Exercise01/sum_bcast.c

sum_scatter: ../Exercise02/sum_scatter.c
	$(CC) -o sum_scatter ../Exercise02/sum_scatter.c

sum_gather: ../Exercise03/sum_gather.c
	$(CC) -o sum_gather ../Exercise03/sum_gather.c

sum_reduce: ../Exercise04/sum_reduce.c
	$(CC) -o sum_reduce ../Exercise04/sum_reduce.c

sum_allreduce: ../Exercise05/sum_allreduce.c
	$(CC) -o sum_allreduce ../Exercise05/sum_allreduce.c

sum_scan: ../Exercise06/sum_scan.c
	$(CC) -o sum_scan ../Exercise06/sum_scan.c

run: all
	mpirun --oversubscribe -np $(NP) ./sum_bcast
	mpirun --oversubscribe -np $(NP) ./sum_scatter
	mpirun --oversubscribe -np $(NP) ./sum_gather
	mpirun --oversubscribe -np $(NP) ./sum_reduce
	mpirun --oversubscribe -np $(NP) ./sum_allreduce
	mpirun --oversubscribe -np $(NP) ./sum_scan

clean:
	rm -f $(PROGRAMS)
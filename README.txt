Last name of Student 1: Hoang
First name of Student 1: Long 
Email of Student 1: longhoang@ucsb.edu



----------------------------------------------------------------------------
Report for Question 1 
How is the code parallelized?
New code at line 30,35 and changing the tid variable 

->changed int variable tid from zero to thread_id XOR with timea ccording to the
provided stackoverflow link

->The new code on line 30 is setting up the following code block for parallelization 
with number of threads equal to threadcnt, and keeping (toss, x, y, distance_squared)
private to each thread process so that they don't tamper with each other results

-> Code added on line 35 is so that the total of valid tosses can be obtain
from the individual results of each processes 

----------------------------------------------------------------------------
Report for Question 2 
How is the code parallelized?

A new code block added from line 80-84 (5 new lines) to set for loop schedule clause
according to what int mappingtype is

A new line at 85 setting up the parallezation process with 
# of threads = threadcnt, and making i,k private so they dont interfere with
each  other result

Two new code lines added at 88 and 93 to parallelize the for loop with 
scheduling according to mappingtype

Total new lines added: 8

----------------------------------------------------------------------------
Parallel time/speedup/efficiency using 2 and 4 cores under different scheduling methods

SERIAL RUNTIME for upper triangular matrix with n = 4096, t = 1024: 
27.60 sec

PARALLEL RUNTIME (2 threads) for upper triangular matrix with n = 4096, t = 1024:
Block Mapping: 15.86 sec
Block Cyclic (r=1): 14.14 sec
Block Cyclic (r=16): 13.94 sec
Dynamic (r=16): 13.9 sec

Speedup:
Block Mapping: 27.60 / 15.86 = 1.74
Block Cyclic (r=1): 27.60 / 14.14 = 1.95
Block Cyclic (r=16): 27.60 / 13.94 = 1.979
Dynamic (r=16): 27.60 / 13.9  = 1.985

Efficiency:
Block Mapping: 1.74 / 2 = 0.87 = 87%
Block Cyclic (r=1): 1.95 / 2 = 0.975 = 97.5%
Block Cyclic (r=16): 1.979 / 2 = 	0.989 = 98.9%
Dynamic (r=16): 1.985 / 2 = 0.992 = 99.2%

PARALLEL RUNTIME (4 threads) for upper triangular matrix with n = 4096, t = 1024:
Block Mapping: 8.57 sec
Block Cyclic (r=1): 7.46 sec
Block Cyclic (r=16): 7.016 sec
Dynamic (r=16): 7.011 sec

Speedup:
Block Mapping: 27.60 / 8.57 = 3.22
Block Cyclic (r=1): 27.60 / 7.46 = 3.69
Block Cyclic (r=16): 27.60 / 7.016 = 3.933
Dynamic (r=16): 27.60 / 7.011 = 3.936

Efficiency:
Block Mapping: 3.22 / 4 = 0.805 = 80.5%
Block Cyclic (r=1): 3.69 / 4 = 0.925 = 92.5%
Block Cyclic (r=16): 3.933 / 4 = 0.983 = 98.3%
Dynamic (r=16): 3.936 / 4 = 0.984 = 98.4%

If there are significant performance differences among different thread scheduling  methods,
provide a short reason. 

There are significant improvement in performance differences when using Cyclic and Dynamic especially when 
chunksize is 16. The reason I think this happens is because less time are spent idle for each of the threads
since in dynamic scheduling if a thread finishes it will get tasks from other thread to do, and for the cyclic
scheduling it keeps the thread active by switching between then after r iterations.


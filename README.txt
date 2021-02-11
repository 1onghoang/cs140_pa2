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


----------------------------------------------------------------------------
Parallel time/speedup/efficiency using 2 and 4 cores under different scheduling methods



If there are significant performance differences among different thread scheduling  methods,
provide a short reason. 



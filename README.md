# CA-Assign-6

Here I had implemented the Hyperquick Sort or simply the quick sort which run on many processors on  processors and ultimately it requires lesser time than any serial quicksort


# Procedure : 

- read input /process 0

- scatter the input data MPI Scatter ()

- Sort each local array for each process using stl qsort ()

- iterate log p times: - 

- create communicator based on process rank and number of iterations 
-    in ith iteration there will be 2i groups of processes or communicaors 
-    also compute the local rank of each process  use MPI Comm split() 
-    process 0 will broadcast its median 
- each process will divide local array into low and high partitioned by median 
- each process in upper half will swap its low list with high list of corresponding

- all of the elements are now in place.

- Process I elements are less than Process i+1 elements

- Gather elements from all processes into process 0 and output to file


 > Commands Used
 - For Compilation 
 - mpicc -g -Wall -o sort hyperquicksort.c -lm

 - For Execution 
 - mpiexec -n num_procs ./sort inputfile outputfile

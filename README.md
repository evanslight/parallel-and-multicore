cpubigarray.c
There is a big array problem for the people Dijsktra and Mandelbrot. 
I rewrite the array set to make it capable with big array

mandelbrot_OPEN.c
It implements mandelbrot set by openMP
example:
gcc mandelbrot_OPEN.c -o mandelbrot_OPEN -lm -fopenmp
./mandelbrot_OPEN 500 500 500


mandelbort_mpi.c
This the mandelbrot_mpi combining openMP and MPI together, 
it can schedule the task by add command -DRC -DDYNAMIC -DSTATIC
-DGUIDED at complie stage
example:
mpicc -fopenmp -o mandelbrot_mpi mandelbrot_mpi.c -DGUIDED -DMAXITERS 1000
mpiexec -n 8 mandelbrot_mpi 500 0
the 500 is the number of pixels
the 0 is the printout node rank

definetest.c
THis is just my practice for the c macro command arguments
example:
gcc definetest.c -o definetest -DMACRO2
./definetest
clear explanation for macro:
http://www.thegeekstuff.com/2012/05/c-macros/

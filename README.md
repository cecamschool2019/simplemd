## COMPILATION

Fortran version:

````
cd fortran
# adjust compile script if necessary
./compile
````

C++ version:

````
cd cpp
# adjust compile script if necessary
./compile
````

## USAGE

A sample `in` file is included in the `input/` directory.
A script `lattice` is also present and can be used to generate initial `xyz` conformations.

````
cd input
./lattice 3 > crystal.xyz
/path/to/simplemd.x < in
````

The allowed keywords are

````
tstep          ! simulation timestep
temperature    ! temperature
friction       ! friction for Langevin dynamics (for NVE, use 0)
listcutoff     ! cutoff for neighbour list
forcecutoff    ! cutoff for forces
nstep          ! number of steps
nconfig        ! stride for output of configurations and file name
nstat          ! stride for output of statistics and file name
maxneighbour   ! maximum average number of neighbours per atom
idum           ! seed
wrapatoms      ! if true, atomic coordinates are written wrapped in minimal cell
outputfile     ! name of the file for the final configuration
inputfile      ! name of the file for the starting configuration
````

trajectories are written as multiple xyz statistics are written as multi column files. Columns correspond to the following quantities:

````
step-number
simulation-time
instantaneous-temperature
configurational-energy
total-energy
conserved-quantity
````
   


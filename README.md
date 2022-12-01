# Glmnet in Matlab
Lasso and elastic-net regularized generalized linear models. See https://web.stanford.edu/~hastie/glmnet_matlab/

This version was updated on Dec 1, 2022 to work with current versions Matlab on the Palmetto cluster at Clemson University. 

## Build instructions

The following instructions indicate how it was built with Matlab 2021b and gcc
9.5.0 on Palmetto and can be used to rebuild for newer versions:

Get on a compute node:
```
qsub -I -l select=1:ncpus=8:mem=12gb,walltime=2:00:00
```

Load appropriate modules (we need gcc for gfortran, and matlab for mex):
```
module load matlab/2021b gcc/9.5.0
```

Recompile the fortran:
```
mex glmnetMex.F GLMnet.f 
```

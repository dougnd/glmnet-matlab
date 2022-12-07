# Glmnet in Matlab
Lasso and elastic-net regularized generalized linear models. See https://web.stanford.edu/~hastie/glmnet_matlab/

This version was updated on Dec 7, 2022 to work with current versions Matlab on the Palmetto cluster at Clemson University. 

The current version requires the Intel compiler in the library path.  You can do this by running the following command before starting matlab:
```
module load intel-oneapi-compilers/2022.1.0-gcc/9.5.0
```

## Build instructions

The following instructions indicate how it was built with Matlab 2022a and intel oneapi compilers on Palmetto and can be used to rebuild for newer versions:

Get on a compute node:
```
qsub -I -l select=1:ncpus=8:mem=12gb,walltime=2:00:00
```

Load appropriate modules (gfortran seemed to produce code that didn't behave correctly, so we use the Intel fortran compiler):

```
module load matlab/2022a intel-oneapi-compilers/2022.1.0-gcc/9.5.0
```

Recompile the fortran (using Intel's compiler -- ifort):
```
mex FC="$(which ifort)" -v glmnetMex.F GLMnet.f
```



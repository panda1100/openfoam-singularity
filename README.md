# openfoam-singularity
Simple Singularity container definition of OpenFOAM v9

## build Singularity container

```
sudo singularity build of9 of9.def
```

## verify

```
./of9 icoFoam -help
```

sample output

```

Usage: icoFoam [OPTIONS]
options:
  -case <dir>       specify alternate case directory, default is the cwd
  -fileHandler <handler>
                    override the fileHandler
  -hostRoots <(((host1 dir1) .. (hostN dirN))>
                    slave root directories (per host) for distributed running
  -libs <(lib1 .. libN)>
                    pre-load libraries
  -listFunctionObjects
                    List functionObjects
  -listScalarBCs    List scalar field boundary conditions (fvPatchField<scalar>)
  -listSwitches     List all available debug, info and optimisation switches
  -listVectorBCs    List vector field boundary conditions (fvPatchField<vector>)
  -noFunctionObjects
                    do not execute functionObjects
  -parallel         run in parallel
  -roots <(dir1 .. dirN)>
                    slave root directories for distributed running
  -srcDoc           display source code in browser
  -doc              display application documentation in browser
  -help             print the usage

Using: OpenFOAM-9 (see https://openfoam.org)
Build: 9-b456138dc4bc

```

## parallel run

```
mpirun -np 8 ./of9 icoFoam -help
```

## interactive shell

```
./of9 bash
Singularity>mkdir -p $WM_PROJECT_USER_DIR
Singularity>mkdir -p $FOAM_RUN
Singularity>run
Singularity>pwd
/home/ubuntu/OpenFOAM/ubuntu-9/run
```


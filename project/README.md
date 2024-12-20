# Gulf Stream
### Project Description

In this project I will aim to understand the effects of the Earth's rotation on the ocean. Specifically, I will analyze the Gulf Stream and the impacts of the Earth's rotation on heat, salinity, and sea surface height.

In an attempt to investigate this, I plan to construct a model of the Gulf Stream, on the East Coast of North America. This model will be for one year ran under two different conditions. One with Earth's normal rotation, and another with angular velocity increased to be twice as fast. The start of the model will be simulated on January 2008. After running the model, I will be able to see how these variables are effected.

### Reproducing Model Results

#### Step 1: Creating Model Files
Create the the input files and add them the input directory.
  - Bathymetry
  - Initial Conditions
  - External Forcing Conditions
  - Boundary Conditions

#### Step 2: Add files to the computing cluster
To move the model files into the computing cluster, create a clone of MITgcm into the scratch directory and make a 'configurations' folder.
```
mkdir MITgcm/configurations/gulf_stream
```
Next, send the `code`, `input`, and `namelist` directorires to the configurations folder with the `scp` command.
#### Step 3: Compile the model
Make a `build` directory and run the commands:
```
../../../tools/genmake2 -of ../../../tools/build_options/darwin_amd64_gfortran -mods ../code -mpi
make depend
make
```

#### Step 4: Run the model
Switch the the run directory, link the contents of `input` and `code`, and then submit the job script:
```
sbatch cs185c.slm
```
#### Step 5: Analyze the Results


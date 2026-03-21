# Simulation Set-up

## icoFoam-Reference - Reference Solution for Cylinder
To properly run the reference simulation, you should consider the following:

### 0 - Removing old data
```bash
foamListTimes -rm
rm -r postProcessing
```

It might also be necessary to remove the VTK file, if that is present.
```
rm -r VTK
```

### 1 - Creating the blockMesh
When initializing the blockMesh I find it better, especially considering we're going to work on multiple meshes, that we do not use:

```bash
blockMesh
```

This initializes the previous blockMeshDict used in the original icoFoam cavity tutorial. Which is not what we are using. To initialize a chosen blockMesh dict we can do the following:

```bash
blockMesh -dict caseDict/blockMeshDict
```

### 2 - Initializing the velocity field
To reduce CPU-time we give the simulation a starting velocity field, which speeds up the time before the system is "dynamically steady". Run:

```bash
setFields
```

### Proper icoFoam-Reference Pre-Processing
```bash
blockMesh -dict caseDict/blockMeshDict		# Creates the correct mesh
checkMesh					# Important to check the blockMesh
setFields					# Initializes the velocity field
```

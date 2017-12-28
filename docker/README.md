# Singularity and Singularity-Python
## Docker containers

`Dockerfile` in the root directory contains the latest releases of Singularity (2.4.2) and Singularity-Python (2.4.1). 

The mentioned Singularity releas has a [known bug](https://github.com/singularityware/singularity/issues/1134) building images from docker container with `aufs` storage driver, the default for `boot2docker`. Changing the storage driver seems to solve the problem

Other folders containing `Dockerfile`s are experimental branches solving this problem. Not yet ready for production.

# DART Containers

## Description
This is a repository for holding Dockerfile recipes for containers built for [DART](https://github.com/NCAR/DART). 
Built images are hosted on the NCAR Dockerhub (no link yet)

## Containers
### dart_dependencies
A container on an Ubuntu base image containing only DART dependencies (DART source not included).

Included packages and libraries:
- libnetcdf-dev
- libnetcdff-dev
- libopenmpi-dev
- netcdf-bin
- build-essentials
- git 

You will need to have Docker Desktop running to build and run the containers.    
Note the example below is pushing to my (hkershaw) docker hub account.

Example build and tag container:    
`docker build --tag hkershaw/dart-dep:1.0 .`   

To run the container:    
`docker run -it hkershaw/dart-dep:1.0 bash`  

To exit the container:    
`exit`  

Push to docker hub:    
`docker push hkershaw/dart-dep:1.0`  


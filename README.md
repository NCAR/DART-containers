# DART Containers

## Description
This is a repository for holding Dockerfile recipes for containers built for [DART](https://github.com/NCAR/DART).  
NCAR does have a dockerhub orgranization: https://hub.docker.com/u/ncar but has currently maxed out its number of users.  

DART Docker images are hosted on the [hkershaw](https://hub.docker.com/repositories/hkershaw) dockerhub.  
If we make more use of containers, we may need to look at creating a DART organization.

## Containers
### dart_dependencies_netcdf-env
A container on an Ubuntu base image containing only DART dependencies (DART source not included).

Included packages and libraries:
- libnetcdf-dev
- libnetcdff-dev
- libopenmpi-dev
- netcdf-bin
- build-essentials
- git 

This container is used in our github actions workflow for [pull requests](
https://github.com/NCAR/DART/blob/e17959db1a917418e192b2c2a6c093dcefb5bdb5/.github/workflows/action_on_pull_request.yml#L15).

You will need to have Docker Desktop running to build and run the containers on your machine.    
Note the example below is pushing to my (hkershaw) docker hub account.

Example build and tag container:

> Note Github runner is amd 64 so if you are building on apple silicon, you will need to build for linux/amd64.   
> `docker buildx build --platform linux/amd64 --tag hkershaw/dart-dep:2.0 .`

`cd dart_dependencies_netcdf-env`  
`docker build --tag hkershaw/dart-dep:1.0 .`   

To run the container:    
`docker run -it hkershaw/dart-dep:1.0 bash`  

> Mac silicon:  
> `docker run -it --platform linux/amd64 hkershaw/dart-dep:1.0 bash`

To exit the container:    
`exit`  



Push to docker hub:    
`docker push hkershaw/dart-dep:1.0`  


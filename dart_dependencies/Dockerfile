# container base image
FROM ubuntu:latest

ENV HOME /home
WORKDIR /home


# fetch package updates and download & install
RUN apt-get -y update; \
	apt-get -y upgrade

# install DART dependencies
RUN apt-get -yq install libnetcdf-dev \
						libnetcdff-dev \
						netcdf-bin \
						libopenmpi-dev \
						git \
						vim \
						build-essential




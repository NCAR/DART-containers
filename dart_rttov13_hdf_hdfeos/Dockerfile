# container base image
FROM ubuntu:latest

ENV HOME /home
ENV NETCDF=/usr/
ENV RTTOV=/home/rttov13_lib/
ENV HDFEOS=/usr/
ENV HDF=/usr/
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
			build-essential \
                        bison \
                        flex \
                        wget \
                        hdf4-tools \
                        libtirpc-dev \
                        libhdf4-dev

RUN wget  -O hdfeos.tar.gz  https://git.earthdata.nasa.gov/projects/DAS/repos/hdfeos/raw/hdf-eos2-3.0-src.tar.gz?at=3128a738021501c821549955f6c78348e5f33850; \
    tar zxvf hdfeos.tar.gz; \
    cd hdf-eos2-3.0 \
    CPPFLAGS='-I/usr/include/hdf' /app/hdf-eos2-3.0/configure --enable-fortran  --prefix=/usr --with-hdf4=/usr --enable-shared; \
    make -j 8; \
    make install; \
    cd ~; \
    rm -rf ~/hdf-eos2-3.0 ~/hdfeos.tar.gz


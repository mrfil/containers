# Create a docker container that contains FSL 6.0.1
# 
# Example usage: 
#

# Start with Centos and CUDA-8.0
FROM nvidia/cuda:8.0-runtime

# Run everything in /root
WORKDIR /root

RUN apt-get -y update; \
	apt-get -y install curl python2.7 libxcb1 libomp-dev libopenblas-dev

# Get the FSL Install Script
RUN curl -O -L https://fsl.fmrib.ox.ac.uk/fsldownloads/fslinstaller.py

# Install FSL
RUN python2.7 fslinstaller.py -d /usr/local/fsl -V 6.0.1

# Setup Shell environment for FSL
ENV FSLDIR=/usr/local/fsl

# Setup FSL Defaults
ENV FSLOUTPUTTYPE=NIFTI_GZ
ENV FSLMULTIFILEQUIT=TRUE
ENV FSLTCLSH=$FSLDIR/bin/fsltclsh
ENV FSLWISH=$FSLDIR/bin/fslwish
ENV FSLLOCKDIR=
ENV FSLMACHINELIST=
ENV FSLREMOTECALL=

ENV PATH=${FSLDIR}/bin:${PATH}

ENV export FSLDIR PATH

RUN ldconfig




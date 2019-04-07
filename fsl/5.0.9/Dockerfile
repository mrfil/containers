# Create a docker container that contains FSL.5.0.9 
# 
# Example usage: 
#

# Start with Centos and CUDA-8.0
FROM nvidia/cuda:8.0-runtime

# Run everything in /root
WORKDIR /root

RUN apt-get -y update; \
	apt-get -y install curl python2.7 libxcb1 libomp-dev

# Get the FSL Install Script
RUN curl -O -L https://fsl.fmrib.ox.ac.uk/fsldownloads/fslinstaller.py

# Install FSL
RUN python2.7 fslinstaller.py -d /usr/local/fsl -V 5.0.9

# Setup Shell environment for FSL
ENV FSLDIR=/usr/local/fsl

RUN echo '. ${FSLDIR}/etc/fslconf/fsl.sh' >> ~/.bash_profile

ENV PATH=${FSLDIR}/bin:${PATH}

ENV export FSLDIR PATH

RUN ldconfig




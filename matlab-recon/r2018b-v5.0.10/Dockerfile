FROM nvcr.io/partners/matlab:r2018b

# let's install FSL for the recon

# Run everything in /root
RUN sudo mkdir /opt/tools; \
    sudo chmod 777 /opt/tools 

WORKDIR /opt/tools

RUN sudo apt-get -y update; \
    sudo apt-get -y install curl python-dev

# Get the FSL Install Script
RUN sudo curl -O -L https://fsl.fmrib.ox.ac.uk/fsldownloads/fslinstaller.py

# Install FSL
RUN sudo /usr/bin/python fslinstaller.py -d /usr/local/fsl -V 5.0.10

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

# Need this for compatibility with singularity
RUN sudo ldconfig

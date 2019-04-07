# Docker Images for Neuroimaging and MR image reconstruction 

## FSL images
Versions available:
 * fsl/5.0.10
 * fsl/5.0.11
 * fsl/6.0.0
 * fsl/6.0.1

FSL is developed by the [FMRIB group](https://fsl.fmrib.ox.ac.uk/fsl/fslwiki/) at Oxford and its use is governed by their [license](https://fsl.fmrib.ox.ac.uk/fsl/fslwiki/Licence).

 ## MATLAB for recon
 Versions available:
  * matlab-recon/r2018b-v5.0.10

  This container installs FSL alongside MATLAB which can be handy for using FSL tools as part of the image reconstruction process. (i.e. skull stripping and phase unwrapping) See above for details about the applicable license governing FSL.

  Please note that the base container is built on the MATLAB for Deep Learning container built by Mathworks and NVIDIA at the [NVIDIA GPU Cloud](https://ngc.nvidia.com/catalog/containers/partners:matlab). The matlab in this container will not function without a valid matlab license, and must be supplied to the container. Documentation on the base container as well as how to supply a valid network or cloud license can be found [here at the mathworks website](https://www.mathworks.com/help/cloudcenter/matlab-deep-learning-container-on-nvidia-gpu-cloud.html).
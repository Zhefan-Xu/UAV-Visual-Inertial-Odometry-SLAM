# VIO Guide for UAV

## VINS-MONO/VINS-Fusion
#### Build (CPU Version)
This part is directly from the original repos. Tested on Ubuntu 16.04 and 18.04.
```
# 1. ROS Pacakges
sudo apt-get install ros-YOUR_DISTRO-cv-bridge ros-YOUR_DISTRO-tf ros-YOUR_DISTRO-message-filters ros-YOUR_DISTRO-image-transport
```
Then, install [cerers-solver](https://github.com/ceres-solver/ceres-solver/releases/tag/1.14.0) (tested with Version 1.14.0). Download the ```ceres-solver-1.14.0.tar.gz``` file from the release page. Then,
```
mv ceres-solver-1.14.0.tar.gz /PATH/TO/YOUR/PACKAGE/LOCATION

# ====================Install Dependencies======================
# CMake
sudo apt-get install cmake
# google-glog + gflags
sudo apt-get install libgoogle-glog-dev libgflags-dev
# Use ATLAS for BLAS & LAPACK
sudo apt-get install libatlas-base-dev
# Eigen3
sudo apt-get install libeigen3-dev
# SuiteSparse and CXSparse (optional)
sudo apt-get install libsuitesparse-dev
```

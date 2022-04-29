# VIO Guide for UAV

## I. VINS-MONO/VINS-Fusion
### a. Installation (CPU Version)
This part is directly from the original repos. Tested on Ubuntu 16.04 and 18.04.

Install related ROS Packages:
```
sudo apt-get install ros-YOUR_DISTRO-cv-bridge ros-YOUR_DISTRO-tf ros-YOUR_DISTRO-message-filters ros-YOUR_DISTRO-image-transport
```
Then, install [ceres-solver](https://github.com/ceres-solver/ceres-solver/releases/tag/1.14.0) (tested with Version 1.14.0). Download the ```ceres-solver-1.14.0.tar.gz``` file from the release page. Then, follow the guide in their [official website](http://ceres-solver.org/installation.html#linux) to build the package.

After successfully installing the ceres solver, you will need to run:
```
sudo make install 
```
Finally, make the packages
```
cd ~/catkin_ws
catkin_make
```

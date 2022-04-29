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
git clone https://github.com/Zhefan-Xu/VINS-PX4
cd ~/catkin_ws
catkin_make
```
### b. Run VINS VIO
First, complete the [calibration](https://github.com/Zhefan-Xu/camera-imu-calibration-guide) part. After getting the parameters, you can modify the parameters of D435i [here for VINS-MONO](https://github.com/Zhefan-Xu/VINS-PX4/tree/main/VINS-Mono/config/realsense) and [here for VINS-Fusion](https://github.com/Zhefan-Xu/VINS-PX4/tree/main/VINS-Fusion/config/realsense_d435i).

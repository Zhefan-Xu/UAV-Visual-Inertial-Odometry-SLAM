# VIO Guide for UAV

## I. VINS-MONO/VINS-Fusion
### a. Installation (CPU Version)
This part is directly from the original repos. Tested on Ubuntu 16.04 and 18.04.

You can find the modified packages for PX4 in this [repo](https://github.com/Zhefan-Xu/VINS-PX4/tree/main/VINS-Fusion/config/realsense_d435i). If you only need VINS-Fusion or VINS-Mono, you can just download one of them. 
```
cd ~/catkin_ws/src
git clone https://github.com/Zhefan-Xu/VINS-PX4
```

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
### b. Run VINS VIO
To run the visual inertial odometry, you need to follow the steps below:
  - Complete the [calibration](https://github.com/Zhefan-Xu/camera-imu-calibration-guide) part. 
  - Modify the parameters of D435i [here for VINS-MONO](https://github.com/Zhefan-Xu/VINS-PX4/tree/main/VINS-Mono/config/realsense) and [here for VINS-Fusion](https://github.com/Zhefan-Xu/VINS-PX4/tree/main/VINS-Fusion/config/realsense_d435i).
  - Turn on D435i camera. Check [this](https://github.com/Zhefan-Xu/camera-imu-calibration-guide/blob/main/rs_d435i.launch) for the launch file:
  ```
  roslaunch realsense2_camera rs_d435i.launch
  ```
  - Connect to PX4:
  ```
  roslaunch mavros px4.launch # you need to setup this yourself
  ```
  - Run VINS-Mono/VINS-Fusion
  ```
  roslaunch vins_estimator vins_mono_d435i_px4.launch # VINS MONO
  ```
  or
  ```
  roslaunch vins vins_fusion_d435i_px4.launch # VINS FUSION
  ```

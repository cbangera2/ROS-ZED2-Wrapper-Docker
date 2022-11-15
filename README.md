# ROS-Melodic-ZED2-Wrapper-Docker
Files to create docker with ROS Melodic and ZED ROS Wrapper

To Build Docker Image:
   1. chmod +x build-ros-desktop-image.sh 
   2. ./build-ros-desktop-image.sh

To Run Docker:
   1. xhost +si:localuser:root
   2. docker run -it --runtime nvidia --privileged -e DISPLAY -v /tmp/.X11-unix:/tmp/.X11-unix 3.7-ros-gl-devel-cuda11.4-ubuntu18.04
   
 


 



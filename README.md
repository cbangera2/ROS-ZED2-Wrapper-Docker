# ROS-Noedic-ZED2-Wrapper-Docker
Files to create docker with ROS Melodic and ZED ROS Wrapper

To Build Docker Image:
   1. ```chmod +x build-ros-desktop-image.sh ```
   2. ```bash build-ros-desktop-image.sh```

To Run Docker for the First Time:
   1. ```xhost +si:localuser:root```
   2. ```docker run -it --runtime nvidia --privileged -e DISPLAY -v /tmp/.X11-unix:/tmp/.X11-unix 3.7-ros-gl-devel-cuda11.4-ubuntu20.04```

Once Enter the Docker Container, you should see: 
   root@(docker conatiner ID):/opt/ros_ws# 
Then Run:
   1. ```source devel/setup.bash```

To Re-enter Docker Container After the First Time:
   1. ```docker start (docker container's name)```
   2. ```docker exec -it (docker container's name) bash```
   
 
 To Run in Docker:
   1. ```roslaunch zed_rtab_example zed_rtabmap.launch```
   2. Wait 5 seconds before moving camera for initialization
   3. ```roslaunch zed_warpper zed2.launch```
   4. ```cd /opt/ros_ws/mdp_cv/src/seg_pkg/scripts```
   5. ```python3 inf_class.py```
   6. ```cd /opt/ros_ws/cv-low-level```
   7. ```python3 hotdog.py```



# ROS-Noedic-ZED2-Wrapper-Docker
Files to create docker with ROS Melodic and ZED ROS Wrapper

To Build Docker Image:
   1. ```chmod +x build-ros-desktop-image.sh ```  
   2. ```bash build-ros-desktop-image.sh```  

## Create Docker Container
To Run Docker for the First Time:
   1. ```xhost +si:localuser:root```  
   2. ```docker run -it --runtime nvidia --privileged -e DISPLAY -v /tmp/.X11-unix:/tmp/.X11-unix 3.7-ros-gl-devel-cuda11.4-ubuntu20.04``` 
   (may add ```--net=host``` flag for communication between docker and jackal)  
To Re-enter Docker Container After the First Time (with Existing container):
   1. ```docker start (docker container's name)```  
   2. ```docker exec -it (docker container's name) bash```  
   
## Setup Docker Container: 
Following precedure are required in every new termainal for docker container  
Once Enter the Docker Container, you should see: 
   root@(docker conatiner ID):/opt/ros_ws#  
Then Run:  
   1. ```source devel/setup.bash```  
Open a New Terminal entering Jackal, Run:  
   3. ```ifconfig``` to obtain inet address under docker0 # For Example, 172.17.0.1  
Then Go Back to Docker Container, Run:  
   3. ```export ROS_Master_URI = http://172.17.0.1:11311/``` # Replace 172.17.0.1 with inet address  

## Run Our Code
 To Run in Docker:
   1. ```roslaunch zed_rtab_example zed_rtabmap.launch```
   2. Wait 5 seconds before moving camera for initialization
   3. ```roslaunch zed_warpper zed2.launch```
   4. ```cd /opt/ros_ws/mdp_cv/src/seg_pkg/scripts```
   5. ```python3 inf_class.py```
   6. ```cd /opt/ros_ws/cv-low-level```
   7. ```python3 hotdog.py```



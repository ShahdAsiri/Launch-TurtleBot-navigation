# Launch-TurtleBot-navigation

First step/ Install Dependents ROS Packages
$ sudo apt-get install ros-noetic-joy ros-noetic-teleop-twist-joy \
  ros-noetic-teleop-twist-keyboard ros-noetic-laser-proc \
  ros-noetic-rgbd-launch ros-noetic-rosserial-arduino \
  ros-noetic-rosserial-python ros-noetic-rosserial-client \
  ros-noetic-rosserial-msgs ros-noetic-amcl ros-noetic-map-server \
  ros-noetic-move-base ros-noetic-urdf ros-noetic-xacro \
  ros-noetic-compressed-image-transport ros-noetic-rqt* ros-noetic-rviz \
  ros-noetic-gmapping ros-noetic-navigation ros-noetic-interactive-markers

Second step/ Install TurtleBot3 packages and
install TurtleBot3 via Debian packages

$ sudo apt-get install ros-kinetic-dynamixel-sdk
$ sudo apt-get install ros-kinetic-turtlebot3-msgs
$ sudo apt-get install ros-kinetic-turtlebot3

Third step/ Install simulation package

$ cd ~/catkin_ws/src/
$ git clone -b noetic-devel https://github.com/ROBOTIS-GIT/turtlebot3_simulations.git
$ cd ~/catkin_ws && catkin_make
Launch Simulation World
Simulation environments have been prepared, including TurtleBot3 World which i used.

$ export TURTLEBOT3_MODEL=waffle
$ roslaunch turtlebot3_gazebo turtlebot3_world.launch
<img width="380" alt="gaza" src="https://github.com/user-attachments/assets/14124655-382a-45a2-966c-7c67ff64ebe8"> 

Fourth step/ Opening SLAM
roslaunch turtlebot3_slam turtlebot3_slam.launch slam_methods:=gmapping

<img width="277" alt="opinning slam" src="https://github.com/user-attachments/assets/46ee78e4-40a4-402f-aaec-3edbea7b66c3">

Fifth step/ Create a map:

rosrun map_server map_saver -f ~/map
then write the command:

roslaunch turtlebot3_teleop turtlebot3_teleop_key.launch

Last step/ navigation
Start the navigation and load the saved map, using this command:

roslaunch turtlebot3_navigation turtlebot3_navigation.launch map_file:='/home/muh/map.yaml'
<img width="299" alt="lastph" src="https://github.com/user-attachments/assets/06fa7d79-4b01-4d4b-8574-a5a908a31a06">


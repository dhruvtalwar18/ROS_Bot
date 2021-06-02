# ROS_Bot

Simulating a 2 wheel differential drive robot for implementing particle filter-based localization of the robot mobile robot by using a single lidar sensor under SLAM in ROS environment

The Following commands need to be run to launch the mybot_ws package
Note: Ubuntu 16.04 and ROS Kinetic have been used to develop this

Clone the repo in the home directory

$ cd mybot_ws\
$ catkin_make\
$ source devel/setup.bash 

$ roslaunch mybot_gazebo mybot_world.launch
$ roslaunch mybot_description mybot_rviz.launch

This shall open the model in the gazebo and RVIZ environment

To move the robot around in the environment 

$ roslaunch mybot_navigation mybot_teleop.launch


Once we are familiar with launching this, we can now start to build maps of the environment

Launch the following in subsequent terminals

$ roslaunch mybot_gazebo mybot_world.launch\
$ roslaunch mybot_navigation gmapping_demo.launch\
$ roslaunch mybot_description mybot_rviz_gmapping.launch

Now we can move the robot around the environement to make an occupancy grid of the environment. 

Once we are happy with the map that can we seen on the rviz simulation we can save the map using

$ rosrun map_server map_saver -f ~/mybot_ws/src/mybot_navigation


<h1><b> Mapping Demonstation </h1></b>

<p align="center"><img src="https://github.com/dhruvtalwar18/ROS_Bot/blob/main/Images/Mapping_GIF_.gif" title="Result 1"></p>

<p align="center">Fig.1 Mapping Demonstration</p>




# ROS_Bot

Simulating a 2 wheel differential drive robot for implementing particle filter-based localization of the robot mobile robot by using a single lidar sensor under SLAM in ROS environment

The Following commands need to be run to launch the mybot_ws package


Download the mybot_ws

$ cd mybot_ws\
$ catkin_make\
$ source devel/setup.bash 

$ roslaunch mybot_gazebo mybot_world.launch
$ roslaunch mybot_description mybot_rviz.launch

This shall open the model in the gazebo and RVIZ environment

To move the robot around in the environment 

$ roslaunch mybot_navigation mybot_teleop.launch




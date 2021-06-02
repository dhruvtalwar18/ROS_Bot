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


Once we are familiar with launching this, we can now start to build maps of the environment

Launch the following in subsequent terminals

$ roslaunch mybot_gazebo mybot_world.launch
$ roslaunch mybot_navigation gmapping_demo.launch
$ roslaunch mybot_description mybot_rviz_gmapping.launch

Now we can move the robot around the environement to make an occupancy grid of the environment. 

Once we are happy with the map that can we seen on the rviz simulation we can save the map using

$ rosrun map_server map_saver -f ~/mybot_ws/src/mybot_navigation





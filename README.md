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


<h1><b> Mapping Demonstration </h1></b>

<p align= "center" ><img align ="center" src="https://github.com/dhruvtalwar18/ROS_Bot/blob/main/Images/Mapping_GIF_.gif" title="Result 1" ></p>

<p align="center">Fig.1 Mapping in ROS environment</p><br><br><br>

We also mapped the lab corridor environment using a UTM-30LX Lidar. We can see the map of the environment as made by the laser scanner. It uses a 3 point occupancy grid using the point cloud data from the 2D lidar. We can see the mapping of the environemnt below.<br>
<br><br>
<p align ="center"><img align ="center" src="https://github.com/dhruvtalwar18/ROS_Bot/blob/main/Images/Corridor_mapping.gif" title="Result 1" ></p>
<p align="center">Fig.2 Mapping in real life environment</p><br><br><br>


<p><img align ="left" src="https://github.com/dhruvtalwar18/ROS_Bot/blob/main/Images/Real%20time%20map%20of%20lab%20corridor_run1.png" title="Result 2" width = "450" height = "170" ><img align ="right" src="https://github.com/dhruvtalwar18/ROS_Bot/blob/main/Images/Real%20time%20map%20of%20lab%20corridor_run2.png" title="Result 3" width = "400" height = "170" ></p><br><br><br><br><br><br><br><br>

<p align="center">Fig.3 Real Life Maps Achieved</p><br><br>


<h1><b> Localization and Navigation Demonstration </h1></b>

To execute localization we first have to launch the robot in the desired environment 

$ roslaunch mybot_gazebo mybot_world.launch\

We will then load the map in the rviz environment

$ roslaunch mybot_navigation amcl_demo.launch  map_file:=<file path/map.yaml>\
$ roslaunch turtlebot_rviz_launchers view_navigation.launch


We can now give any point on the map as the goal and the robot shall reach it. he robot is localized according to the map frame in the global map, and relative to its position we can get the coordinates of the robot.

<p align ="center"><img align ="center" src="https://github.com/dhruvtalwar18/ROS_Bot/blob/main/Images/Navigation_1.gif" title="Result 4" ></p>
<p align="center">Fig.4 Navigation Demo in ROS environment </p><br><br>

Simulations were carried out to see if the localization of the robot was accurate enough to guide itself from the obstacle which is not present on the global map. The result shwon in Fig. 5 shows that the path planning algorithm now calculates an alternative global path and again the local path follows the global path, 

  
<p align ="center"><img align ="center" src="https://github.com/dhruvtalwar18/ROS_Bot/blob/main/Images/Dynamic_Obs.gif" title="Result 4" ></p>
<p align="center">Fig.4 Navigation Demo in ROS environment </p><br><br>

 









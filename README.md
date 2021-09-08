# Widowx-arm-Move-Group-Python-Interface

Author name: Amna Mazen Ali

In this tutorial I will show you step by step how to  give a series of joint goals for widowx arm using Move Group Python Interface


The simplest way to use MoveIt through scripting is using the move_group_interface. This interface is ideal for beginners and provides unified access to many of the features of MoveIt.

1- Move Group C++ Interface

2- Move Group Python Interface

3- MoveIt Commander Scripting


One of the simplest MoveIt user interfaces is through the Python-based Move Group Interface. In this tutorial, I used code of moveit Documentation and modified it 
to be suitable for widowx arm:
http://docs.ros.org/en/kinetic/api/moveit_tutorials/html/doc/move_group_python_interface/move_group_python_interface_tutorial.html



# Create move_group_python_interface package


* Let's have a look on the required libraries to be imported in our file to decide the dependencies of our package

> import sys

> import copy

> import rospy

> import moveit_commander

> import moveit_msgs.msg

> import geometry_msgs.msg

> from math import pi

> from std_msgs.msg import String

> from moveit_commander.conversions import pose_to_list

* To use the Python MoveIt interfaces, we will import the moveit_commander namespace. This namespace provides us with a MoveGroupCommander class, 
a PlanningSceneInterface class, and a RobotCommander class.

$ cd widowx_arm/src

$ catkin_create_pkg move_group_python_interface rospy moveit_commander moveit_msgs geometry_msgs std_msgs

* Create a "src" folder inside the package and paste "move_group_python_interface_tutorial.py"

* To make this file as executable file

$ sudo chmod +x move_group_python_interface_tutorial.py

$ cd ..

$ catkin_make


# Launch widowx moveit package:

* First, we need to launch widowx moveit package:


$ sudo chmod 777 /dev/ttyUSB0

$ cd ~/widowx_arm

$ source devel/setup.bash

$ roslaunch widowx_arm_bringup arm_moveit.launch sim:=false sr300:=false



# Run move_group_python_interface_tutorial node

$ rosrun move_group_python_interface move_group_python_interface_tutorial.py

# Planning for a goal

1) Planning to a Joint Goal: in this method, we get the joint values from the group and adjust some of the values.
2) Planning to a Pose Goal:We can plan a motion for this group to a desired pose for the end-effector
3) Cartesian Paths: You can plan a Cartesian path directly by specifying a list of waypoints for the end-effector to go through


* In this file, two joint goals are given for "widowx_arm" group and one joint goal for "widowx_gripper" group to open the gripper.

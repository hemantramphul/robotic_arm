# Modeling a robotic arm
This assignment is divided into three parts: creating an urdf, integrating the urdf into MoveIt and creating a service to drive the arm.

#### Authors

- [Hemant Ramphul](https://www.github.com/hemantramphul/)
- [Lav Singh Ramessur](https://www.github.com/Lav-Singh/)



## Introduction 
1. In the first part it is a question of setting up the __*urdf*__ of an existing robot, of to be able to visualize it on __*Rviz*__ and move the joints.
2. In the second part, having an *urdf of the robot* it will be necessary to integrate it on __*Moveit*__ in order to be able to control the trajectory of the robot.
3. In the last part it is a question of __*creating two services*__, one for the kinematics *direct* and the other for *indirect* kinematics.

### Part 1. Creation of the urdf
Creating a workspace for catkin
```bash
$ mkdir -p ~/catkin_ws/src
```
Build catkin workspace:
```bash
$ cd ~/catkin_ws/
$ catkin_make
```
Init the environment:
```bash
$ source devel/setup.sh
```
Create a new package called **'ri_arm_description'**
```bash
$ catkin_create_pkg ri_arm_description rospy roscpp urdf std_msgs geometry_msgs sensor_msgs
```
Building acatkin workspace and sourcing the setup file
```bash
$ catkin_make
```
Create a URDF file named **"robot.urdf"**
```bash
$ mkdir -p urdf/robot.urdf
```
Set permisson **777** to file
```bash
$ chmod +x *
```
To view on **RVIZ**, run the following command: 
```bash
$ roslaunch ri_arm_description display.launch model:=robot.urdf
```

### Part 2. Integration of urdf in MoveIt
Start the robotic arm in **MoveIt** using command.
```bash
$ roslaunch moveit_setup_assistant setup_assistant.launch
```
after that a start screen will bring up like This
![Start Screen](contents/MoveIt_setup_assistant_launch.png)

Create New MoveIt Configuration Package: (Click on the browse button and navigate to the **"robot.urdf"** file)

Add Planning Groups
Create a group named **"ri_arm"**
![Create Group](contents/group.png)

Select all joints collections
![Groups selections](contents/groups.png)

Create a pose named **"Pose"** to reset initial position of your robot arm.
![Create Pose](contents/create_pose.png)

And finally create your package **"ri_arm_config"**
![Create Package](contents/create_pkg.png)

_Demo via RViz to play plainning group_
![Demo](https://github.com/hemantramphul/robotic_arm/assets/7212627/02d44ac3-0c2e-4c6d-8b6e-4561f5fe0eba)

### Part 3. Creation of control services
Create a package "ri_arm_control".

Create a "launch" folder
```bash
$ mkdir launch
```

Create two files namely **"direct.launch"** and indirect **"indirect.launch"**

Config all nodes for **"direct.launch"**
```xml
<launch>
	<node name="first_arm_controller" pkg="ri_arm_control" type="direct_kin_service.py">
		<param name="ri_arm" value="first_to_second_pivot" />
	</node>
	<node name="second_arm_controller" pkg="ri_arm_control" type="direct_kin_service.py">
		<param name="ri_arm" value="second_pivot_to_second" />
	</node>
	<node name="third_arm_controller" pkg="ri_arm_control" type="direct_kin_service.py">
		<param name="ri_arm" value="third_pivot_to_second" />
	</node>
</launch>
```

Config to reset **"indirect.launch"**
```xml
<launch>
	<node name="arm_controller" pkg="ri_arm_control" type="indirect_kin_service.py">
		<param name="ri_arm" value="POSE" />
	</node>
</launch>
```

Launch direct kinematics
```bash
$ roslaunch ri_arm_control direct.launch
```

Launch indirect kinematics
```bash
$ roslaunch ri_arm_control indirect.launch
```

#### Plugins and others

| Plugins             | Source                                                                 |
| ----------------- | ------------------------------------------------------------------ |
| ROS Noetic | https://wiki.ros.org/noetic |
| MoveIt | https://moveit.ros.org/ |
| Gazebo | https://gazebosim.org/home |

## 🚀 About Me
<h3>
  Hi there 👋 I'm Hemant 👨‍💻
</h3>

<p>
  A full stack developer from Mauritius. 
</p>

<p>  
  <a href="https://www.linkedin.com/in/hemantramphul/">
    <img src="https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white" />
  </a>&nbsp;&nbsp;
  <a href="https://github.com/hemantramphul/">
    <img src="https://img.shields.io/badge/GitHub-100000?style=for-the-badge&logo=github&logoColor=white" />        
  </a>&nbsp;&nbsp;
  <a href="https://stackoverflow.com/users/3537318/hemant-ramphul">
    <img src="https://img.shields.io/badge/Stack_Overflow-FE7A16?style=for-the-badge&logo=stack-overflow&logoColor=white" />        
  </a>&nbsp;&nbsp;  
  <a href="https://www.facebook.com/hramphul/">
    <img src="https://img.shields.io/badge/Facebook-1877F2?style=for-the-badge&logo=facebook&logoColor=white" />        
  </a>&nbsp;&nbsp;  
</p>

<p>
  <a href="#"><img src="https://github-readme-stats.vercel.app/api?username=hemantramphul&show_icons=true&count_private=true&theme=dark" width="350"></a>
</p>

___

##### Université des Mascareignes (UdM)
Faculty of Information and Communication Technology <br>
Master Artificial Intelligence and Robotics <br>
Official Website: https://udm.ac.mu <br>


**Free Software, Source Code, Enjoy!** 👋

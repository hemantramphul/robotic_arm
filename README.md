# Modeling a robotic arm
This assignment is divided into three parts: creating an urdf, integrating the urdf into MoveIt and creating a service to drive the arm.

#### Authors

- [Hemant Ramphul](https://www.github.com/hemantramphul)
- [Lav Singh Ramessur](https://github.com/Lav-Singh/)



## Introduction 
1. In the first part it is a question of setting up the __*urdf*__ of an existing robot, of to be able to visualize it on __*Rviz*__ and move the joints.
2. In the second part, having an *urdf of the robot* it will be necessary to integrate it on __*Moveit*__ in order to be able to control the trajectory of the robot.
3. In the last part it is a question of __*creating two services*__, one for the kinematics *direct* and the other for *indirect* kinematics.

#### Part 1. Creation of the urdf
Creating a workspace for catkin
```
$ mkdir -p ~/catkin_ws/src
```
Build catkin workspace:
```
$ cd ~/catkin_ws/
$ catkin_make
```
Init the environment:
```
$ source devel/setup.sh
```
Create a new package called **'ri_arm_description'**
```
$ catkin_create_pkg ri_arm_description rospy roscpp urdf std_msgs geometry_msgs sensor_msgs
```
Building acatkin workspace and sourcing the setup file
```
$ catkin_make
```
Create a URDF file named **"robot.urdf"**
```
$ mkdir -p urdf/robot.urdf
```
Set permisson **777** to file
```
$ chmod x+ *
```
Control with **Rviz**
```
$ roslaunch ri_arm_config demo.launch rviz_tutorial:=true
```

#### Part 2. MoveIt



#### Plugins and others

| Plugins             | Source                                                                 |
| ----------------- | ------------------------------------------------------------------ |
| ROS Noetic | https://wiki.ros.org/noetic |
| MoveIt | https://moveit.ros.org/ |
| Gazebo | https://gazebosim.org/home |

## 🚀 About Me
<h1>
  Hi there 👋 I'm Hemant 👨‍💻
</h1>

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

# Controlling-the-robot-arm-by-join_state_publisher
## step 1: setup a ROS workspace (Catkin)

mkdir catkin_ws

then you can go inside your new folder:

cd catkin_ws

then we are going to create a source (make sure it exactly src inside the catkin work space)

mkdir src

now make sure that you are inside the catkin_ws folder not inside the (src folder) then u can start to cmopile by running the command:

catkin_make

![Screenshot 2024-08-03 081227](https://github.com/user-attachments/assets/f61b7c0e-1e8d-41a0-bb58-395e0c73e50e)

## step 2:
if you running the command 1s, you can see that you have 2 wnew folders (build, devel)
![Screenshot 2024-08-03 081908](https://github.com/user-attachments/assets/be3ed847-2eee-4313-b9ac-629a69b1cd35)

source the setup file 

Navigate to the devel director and list it's contents:

cd devel/

ls

- cd devel/ changes the current directory to devel, where Catkin stores built products and environment setup files.
- 
- ls lists the contents of the devel directory. You should see various setup scripts.

This command runs the setup.bash script, setting up the environment to use the ROS packages built in the workspace. It configures the environment variables needed by ROS tools and packages.

Now make sure to write your codes sequentially and correctly, as shown in the image I will show you now.
![Screenshot 2024-08-03 081908](https://github.com/user-attachments/assets/855ab6c1-9d22-4f73-be6a-f9292e9da229)

on the last code that was ( gedit ~/.bashrc ) click enter.

then this window will appears 
![Screenshot 2024-08-03 081930](https://github.com/user-attachments/assets/f3f15ce7-888a-43dd-81ed-0d9d8708aa80)

At the end of this window, at line 119, you can see the source line for our global ROS installation. We will add the line source ~/catkin_ws/devel/setup.bash after the global ROS installation.
![Screenshot 2024-08-03 082528](https://github.com/user-attachments/assets/27b7c0fd-dd10-442e-af69-594bef477cfb)

then click (Save) and quit the file. You should have those two lines, which represent your global ROS installation as the first level and your custom workspace as the second level. You need to source both the global ROS installation and your Catkin workspace to use your code with ROS functionalities.

Now everthing is good, let's complete the steps together.

## installing the package arduino_robot_arm
now write all this codes step by step 

1- first write scd src 

2- then write sudo apt install git 

3- then git clone https://github.com/smart-methods/arduino_robot_arm

4- now go back to the (catkin_ws) using command cd .. 

then write rosdep install --from-paths src --ignore-src -r -y

5- run the command sudo apt-get install ros-noetic-moveit

6- then sudo apt-get install ros-noetic-joint-state-publisher ros-noetic-joint-state-publisher-gui

7- sudo apt-get install ros-noetic-gazebo-ros-control joint-state-publisher

8- sudo apt-get install ros-noetic-ros-controllers ros-noetic-ros-control

now you shouls compile the package by this code 

9- finall step write catkin_make then click enter.

## Controlling the motors
now you can control the motors by this commend

- run this command the widows will apears
  roslaunch robot_arm_pkg check_motors.launch

  now you can move it as you like


  ## Gazebo
  write this commend then the window will show to you
 roslaunch robot_arm_pkg check_motors_gazebo.launch

 ## MoveIt controlling
 finally write 
 roslaunch moveit_pkg demo.launch

## Now you finished, you did a great.
  


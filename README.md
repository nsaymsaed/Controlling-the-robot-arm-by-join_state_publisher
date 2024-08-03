# Controlling-the-robot-arm-by-join_state_publisher
## step 1: setup a ROS workspace (Catkin)
mkdir catkin_ws
then you can go inside your new folder:
cd catkin_ws
then we are going to create a source (make sure it exactly src inside the catkin work space)
mkdir src
now make sure that you are inside the catkin_ws folder not inside the (src folder) then u can start to cmopile by running the command:
catkin_make

## step 2:
if you running the command 1s, you can see that you have 2 wnew folders (build, devel)
source the setup file 
Navigate to the devel director and list it's contents:
cd devel/
ls
- cd devel/ changes the current directory to devel, where Catkin stores built products and environment setup files.
- ls lists the contents of the devel directory. You should see various setup scripts.
This command runs the setup.bash script, setting up the environment to use the ROS packages built in the workspace. It configures the environment variables needed by ROS tools and packages.

Now make sure to write your codes sequentially and correctly, as shown in the image I will show you now.

on the last code that was ( gedit ~/.bashrc ) click enter.
then this window will appears 

At the end of this window, at line 119, you can see the source line for our global ROS installation. We will add the line source ~/catkin_ws/devel/setup.bash after the global ROS installation.
then click (Save) and quit the file. You should have those two lines, which represent your global ROS installation as the first level and your custom workspace as the second level. You need to source both the global ROS installation and your Catkin workspace to use your code with ROS functionalities.
Now everthing is good, let's complete the steps together.

## installing the package arduino_robot_arm
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
9- catkin_make 


# SLAM-Final-Year-Project
This is the project repository of my final year project during degree studies.

1. This project requires the Ubuntu 18.04 (Bionic Beaver) and Robot Operating System (ROS) Melodic Morenia

2. Install the packages below:
- Gazebo
- Turtlebot3
- RViz

3. Create the catkin workspace then open the workspace directory in the linux terminal.

4. Run these commands in the terminal: 

Install Gazebo:
sudo apt-get install ros-melodic-gazebo-ros-pkgs ros-melodic-gazebo-ros-control

Install Turtlebot3
source /opt/ros/melodic/setup.bash
sudo apt-get install ros-melodic-turtlebot3-msgs
sudo apt-get install ros-melodic-turtlebot3

Build the packages:
cd catkin_ws/src
git clone -b melodic-devel https://github.com/ROBOTIS-GIT/turtlebot3
git clone -b melodic-devel https://github.com/ROBOTIS-GIT/turtlebot3_simulations
cd ..
catkin_make
source /devel/setup.bash

Navigation Stack:
sudo apt-get install ros-melodic-navigation
cd catkin_ws/src
git clone -b melodic-devel https://github.com/ros-planning/navigation
cd ..
catkin_make
source /devel/setup.bash

5. Running the project

Setting up the robot:
export TURTLEBOT3_MODEL=waffle_pi
source ~/.bashrc

Launch the virtual environment in Gazebo:
roslaunch ros_autonomous_slam turtlebot3_world.launch

Launch the rviz to start the visual of mapping and localisation:
roslaunch ros_autonomous_slam autonomous_explorer.launch 

To start the autonomous robot, select the publish point tool in the rviz software.
Then publish points 5 times in the highlighted square area,
the first one is at the upper left corner,
the second one is at the lower left corner,
the third one is at the lower right corner,
the fourth one is at the upper right  corner,
the last point is on the robot itself.

After the mapping has come to satisfaction, you can generate the map by running:
rosrun map_server map_saver -f my_map

The output folder of the map is in the catkin workspace folder.

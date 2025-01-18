#SLAM Final Year Project
This repository contains the code and setup instructions for my final year project during my degree studies. The project focuses on creating an autonomous robot using SLAM (Simultaneous Localization and Mapping) to explore an environment and build a map using ROS and Gazebo.

##Prerequisites
Ubuntu 18.04 (Bionic Beaver)

Robot Operating System (ROS) Melodic Morenia

Required Packages
Gazebo

Turtlebot3

RViz

Navigation Stack

Installation
Follow the steps below to set up the environment and install the necessary packages.

1. Install Gazebo
Open a terminal and run the following command to install Gazebo and related ROS packages:

bash
sudo apt-get install ros-melodic-gazebo-ros-pkgs ros-melodic-gazebo-ros-control
2. Install Turtlebot3
Source ROS setup and install Turtlebot3 packages:

bash
source /opt/ros/melodic/setup.bash
sudo apt-get install ros-melodic-turtlebot3-msgs
sudo apt-get install ros-melodic-turtlebot3
3. Create and Build Catkin Workspace
Create a catkin workspace and clone the required repositories:

bash
cd ~
mkdir -p catkin_ws/src
cd catkin_ws/src
git clone -b melodic-devel https://github.com/ROBOTIS-GIT/turtlebot3
git clone -b melodic-devel https://github.com/ROBOTIS-GIT/turtlebot3_simulations
cd ..
catkin_make
source devel/setup.bash
4. Install Navigation Stack
Install the navigation stack package:

bash
sudo apt-get install ros-melodic-navigation
Clone the navigation repository:

bash
cd catkin_ws/src
git clone -b melodic-devel https://github.com/ros-planning/navigation
cd ..
catkin_make
source devel/setup.bash
Setting Up the Robot
Before launching the project, you need to set up the Turtlebot3 model:

bash
export TURTLEBOT3_MODEL=waffle_pi
source ~/.bashrc
Running the Project
1. Launch Virtual Environment in Gazebo
To launch the robot's environment in Gazebo, run the following command:

bash
roslaunch ros_autonomous_slam turtlebot3_world.launch
2. Launch RViz for Visualization
To visualize mapping and localization, launch RViz with the following:

bash
roslaunch ros_autonomous_slam autonomous_explorer.launch
3. Start Autonomous Robot Exploration
In RViz, use the Publish Point Tool to specify target points for the robot to explore. Publish the following points in the highlighted square area:

Upper left corner

Lower left corner

Lower right corner

Upper right corner

On the robot itself

The robot will autonomously explore the environment and generate a map.

4. Generate the Map
Once the mapping is complete and satisfactory, generate the map with:

bash
rosrun map_server map_saver -f my_map
The generated map will be saved in the catkin_ws folder.

Conclusion
This project allows you to set up and operate an autonomous robot using SLAM to map and explore an environment using ROS, Gazebo, and Turtlebot3. Follow the above steps to get the system up and running and generate your map!


# SLAM Final Year Project

This repository contains the code and setup instructions for my final year project during my degree studies. The project focuses on creating an autonomous robot using SLAM (Simultaneous Localization and Mapping) to explore an environment and build a map using ROS and Gazebo.

## Prerequisites

- **Ubuntu 18.04 (Bionic Beaver)**
- **Robot Operating System (ROS) Melodic Morenia**

### Required Packages

- Gazebo
- Turtlebot3
- RViz
- Navigation Stack

## Installation

Follow the steps below to set up the environment and install the necessary packages.

### 1. Install Gazebo

Open a terminal and run the following command to install Gazebo and related ROS packages:

```bash
sudo apt-get install ros-melodic-gazebo-ros-pkgs ros-melodic-gazebo-ros-control

# Robotics_Bitmask
Low Prep PS Submission for Robotics Problem Statement by Contingent "Bitmask", for STC General Championship - Tech, 2025.

## Table of Contents
- 


## Installation

Ensure that you have ROS2 Jazzy installed. If not, install it from [here](https://docs.ros.org/en/jazzy/Installation/Ubuntu-Install-Debs.html)

Once you have ROS2 setup, then install Gazebo Harmonic using the following commmands 
'''
sudo apt-get install curl
sudo curl https://packages.osrfoundation.org/gazebo.gpg --output /usr/share/keyrings/pkgs-osrf-archive-keyring.gpg
echo "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/pkgs-osrf-archive-keyring.gpg] http://packages.osrfoundation.org/gazebo/ubuntu-stable $(lsb_release -cs) main" | sudo tee /etc/apt/sources.list.d/gazebo-stable.list > /dev/null
sudo apt-get update
sudo apt-get install gz-harmonic
'''

Now, clone this package into your Turtlebot 4 workspace
'''
cd ~
mkdir turtlebot4_ws
mkdir turtlebot_ws/src
cd turtlebot4_ws/src
git clone https://github.com/YogeshwarSingh10/Robotics_Bitmask.git -b Jazzy
'''
Install relevant dependencies
'''
cd ~/turtlebot4_ws
rosdep install --from-path src -yi
'''
Build Packages
'''
source /opt/ros/jazzy/setup.bash
colcon build --symlink-install
'''
Source the workspace
'''
source ~/turtlebot4_ws/install/setup.bash
echo 'source ~/turtlebot4_ws/install/setup.bash' >> ~/.bashrc
'''



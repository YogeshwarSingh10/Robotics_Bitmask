# Instructions for ROS2 Jazzy

## Table of Contents
- [Installation](#installation)
- [Launching the Simulation](#launching-the-simulation)
- [Moving the robot and generating Map](#moving-the-robot-and-generating-map)
- [Multiple robots](#multiple-robots)


## Installation

Ensure that you have ROS2 Jazzy installed. If not, install it from [here](https://docs.ros.org/en/jazzy/Installation/Ubuntu-Install-Debs.html)

Once you have ROS2 setup, then install Gazebo Harmonic using the following commmands 
```
sudo apt-get install curl
sudo curl https://packages.osrfoundation.org/gazebo.gpg --output /usr/share/keyrings/pkgs-osrf-archive-keyring.gpg
echo "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/pkgs-osrf-archive-keyring.gpg] http://packages.osrfoundation.org/gazebo/ubuntu-stable $(lsb_release -cs) main" | sudo tee /etc/apt/sources.list.d/gazebo-stable.list > /dev/null
sudo apt-get update
sudo apt-get install gz-harmonic
```

Now, clone this package into your Turtlebot 4 workspace
```
cd ~
mkdir turtlebot4_ws
mkdir turtlebot_ws/src
cd turtlebot4_ws/src
git clone https://github.com/YogeshwarSingh10/Robotics_Bitmask.git
```
Install relevant dependencies
```
cd ~/turtlebot4_ws
rosdep install --from-path src -yi
```
Build Packages
```
source /opt/ros/jazzy/setup.bash
colcon build --symlink-install
```
Source the workspace
```
source ~/turtlebot4_ws/install/setup.bash
echo 'source ~/turtlebot4_ws/install/setup.bash' >> ~/.bashrc
```

## Launching the Simulation
Use the following command to launch the robot in the Dynamic Warehouse.
```
ros2 launch turtlebot4_gz_bringup turtlebot4_gz.launch.py
```
## Moving the robot and generating Map
You can give it a velocity from the Terminal
```
ros2 topic pub /cmd_vel geometry_msgs/msg/TwistStamped "{header: {stamp: {sec: 0, nanosec: 0}, frame_id: 'base_link'}, twist: {linear: {x: 0.3, y: 0.0, z: 0.0}, angular: {x: 0.0, y: 0.0, z: 0.2}}}"
```

Now, run SLAM.
```
ros2 launch turtlebot4_navigation slam.launch.py
```
View the map in Rviz2
```
ros2 launch turtlebot4_viz view_navigation.launch.py
```
## Multiple robots
To launch two robots at the same time, run the following command. Note that both are under separate namespaces
```
ros2 launch turtlebot4_gz_bringup turtlebot4_gz.launch.py namespace:=/robot1 
ros2 launch turtlebot4_gz_bringup turtlebot4_spawn.launch.py namespace:=/robot2 x:=0.0 y:=1.0 
```




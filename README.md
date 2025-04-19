# Instructions for ROS2 Humble




## Setup

Open a new terminal and enter the following commands

```bash
  mkdir turtlebot4_ws
  cd turtlebot4_ws
  git clone https://github.com/YogeshwarSingh10/Robotics_Bitmask.git -b Humble
```

 Open a new terminal(this will spawn the model in gazebo sim)
```bash
  export IGN_IP=127.0.0.1
  export LIBGL_ALWAYS_SOFTWARE=true
  cd turtlebot4_ws
  source install/setup.bash
  ros2 launch turtlbot4_ignition_bringup turtlebot4_ignition.launch.py
```
Open a new terminal(this is for enabling teleop twist keyboard)
```bash
  sudo apt install ros-humble-teleop-twist-keyboard
  source install/setup.bash
  ros2 run teleop_twist_keyboard teleop_twist_keyboard

```
Open a new terminal (for slam)
```bash
  cd turtlebot4_ws
  source install/setup.bash
  ros2 launch turtlebot4_navigation slam.launch.py
```
Open a new terminal(for rviz)
```bash
  cd turtlebot4_ws
  source install/setup.bash
  ros2 launch turtlebot4_viz view_robot.launch.py
```

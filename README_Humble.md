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
![Screenshot from 2025-04-19 23-27-47](https://github.com/user-attachments/assets/40e52746-a8db-4c74-9cf8-d45842f30b8f)
![Screenshot from 2025-04-19 23-28-28](https://github.com/user-attachments/assets/cf62e3bb-51f0-456d-8f72-2079e2d7c354)
![Screenshot from 2025-04-19 23-29-33](https://github.com/user-attachments/assets/64e54fa5-38fb-4d4e-83b9-5fbe6ff8b855)
![Screenshot from 2025-04-19 23-29-54](https://github.com/user-attachments/assets/67c510f8-5b8d-445a-89ba-5e272d623d75)

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


# ROS 2 Humble — Short Command Reference

These commands summarize the learning activities discussed in the [academic report](ROS2_FUNDAMENTALS_TECHNICAL_REPORT.pdf). They assume the appropriate package is installed and the ROS 2 Humble environment is sourced.

## Simulator and graph inspection

```bash
source /opt/ros/humble/setup.bash
ros2 run turtlesim turtlesim_node
ros2 run turtlesim turtle_teleop_key
ros2 node list
ros2 node info /turtlesim
ros2 topic list -t
ros2 topic echo /turtle1/cmd_vel
ros2 interface show geometry_msgs/msg/Twist
ros2 run rqt_graph rqt_graph
```

## Topics and services

```bash
ros2 topic hz /turtle1/pose
ros2 topic bw /turtle1/pose
ros2 service list -t
ros2 interface show turtlesim/srv/Spawn
ros2 service call /spawn turtlesim/srv/Spawn '{x: 2.0, y: 2.0, theta: 0.2, name: "turtle2"}'
```

## Parameters and actions

```bash
ros2 param list
ros2 param get /turtlesim background_g
ros2 param set /turtlesim background_r 150
ros2 param dump /turtlesim > turtlesim.yaml
ros2 action list -t
ros2 action info /turtle1/rotate_absolute
ros2 action send_goal /turtle1/rotate_absolute turtlesim/action/RotateAbsolute '{theta: -1.57}' --feedback
```

## Build workflow

```bash
mkdir -p ~/ros2_ws/src
cd ~/ros2_ws
source /opt/ros/humble/setup.bash
colcon build --symlink-install
source install/setup.bash
ros2 pkg create --build-type ament_cmake --license Apache-2.0 --node-name my_node my_package
```

**Note:** The commands document standard instructional workflows, not a newly executed automated test suite. The original organization-specific source report is not published.

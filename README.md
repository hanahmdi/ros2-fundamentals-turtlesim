# ROS 2 Fundamentals — Turtlesim and Robotics Middleware

**An educational ROS 2 learning project focused on command-line tools, middleware communications, simulation workflows, and ROS package development.**

The exercises use **ROS 2 Humble**, **Ubuntu Linux**, and the standard **Turtlesim** teaching environment to study how independently running robotics components communicate and how developers inspect, configure, build, and launch them.

## Full Technical Report

**[Read the complete English academic report (PDF)](docs/ROS2_FUNDAMENTALS_TECHNICAL_REPORT.pdf)**

The 16-page A4 report contains the conceptual foundations, annotated ROS 2 command examples, architectural diagrams, an integrated practice sequence, an appendix of useful commands, and a discussion of project limitations.

## Topics Covered

| Area | Topics and activities |
| --- | --- |
| ROS 2 fundamentals | ROS 1 vs. ROS 2, DDS, distributed discovery, ROS graph |
| Simulator setup | Ubuntu environment, ROS 2 Humble, Turtlesim startup and teleoperation |
| Nodes | Node discovery, inspection, naming and remapping |
| Topics | Publisher/subscriber communication, `geometry_msgs/msg/Twist`, `echo`, `hz`, `bw` |
| Services | Service types, `/spawn`, two-turtle interaction |
| Parameters | Runtime configuration, YAML export and import |
| Actions | `RotateAbsolute`, goals, feedback and cancellation concepts |
| Diagnostics | `rqt`, `rqt_graph`, `rqt_console` and logging levels |
| Launch | Coordinated startup, namespaces and multiple simulator instances |
| Workspace tools | `colcon`, underlay/overlay sourcing, standard ROS 2 examples |
| Packaging | `ament_cmake`, package metadata, minimal C++ package scaffolding |

## Basic Demonstration

With ROS 2 Humble installed on a compatible Ubuntu system:

```bash
source /opt/ros/humble/setup.bash
sudo apt install ros-humble-turtlesim
ros2 run turtlesim turtlesim_node
```

Open a second terminal, source the same environment, and run:

```bash
ros2 run turtlesim turtle_teleop_key
```

Inspect communication in another sourced terminal:

```bash
ros2 node list
ros2 topic list -t
ros2 topic echo /turtle1/cmd_vel
ros2 interface show geometry_msgs/msg/Twist
```

The full report explains these commands alongside services, parameters, actions, graphical tools, launch mechanisms, and package management.

## Project Overview

This project documents hands-on exploration of ROS 2 fundamentals through Turtlesim simulation, command-line tools, and practical exercises in node communication, topics, services, actions, parameters, launch configurations, and workspace management. It demonstrates foundational skills in robotics middleware and ROS 2 development workflows.

## Author

**Hannaneh Sadat Ahmadi**

## Resources

- [ROS 2 Humble documentation](https://docs.ros.org/en/humble/)
- [ROS website](https://www.ros.org/)
- [ROS 2 example applications](https://github.com/ros2/examples)
- [colcon documentation](https://colcon.readthedocs.io/)

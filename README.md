# Docker-ROS2

## What is this?

* A Docker container for ROS2 and Gazebo.
* GUI is enabled if WSLg is installed.


## Prerequisites

* docker, docker-compose
* (Optional) WSLg


## Getting started

```bash
git clone {this-repository}
cd {this-repository}
docker-compose build
docker-compose up -d
docker-compose exec ros2 bash
```

### ROS2

From [Introducing turtlesim and rqt — ROS 2 Documentation: Galactic documentation](https://docs.ros.org/en/galactic/Tutorials/Turtlesim/Introducing-Turtlesim.html#start-turtlesim)

```bash
ros2 run turtlesim turtlesim_node
```

### Gazebo

From [Testing Gazebo and ROS 2 integration | Gazebo : Tutorial](https://gazebosim.org/tutorials?tut=ros2_installing&cat=connect_ros#TestingGazeboandROS2integration)


```bash
gazebo --verbose /opt/ros/galactic/share/gazebo_plugins/worlds/gazebo_ros_diff_drive_demo.world
```

Open another terminal

```bash
ros2 topic pub /demo/cmd_demo geometry_msgs/Twist '{linear: {x: 1.0}, angular: {z: 1.0}}' -1
```


## Set up your workspace

You may better to follow this steps to set up your workspace.
[Creating a workspace — ROS 2 Documentation: Galactic documentation](https://docs.ros.org/en/galactic/Tutorials/Workspace/Creating-A-Workspace.html)


## Other commands

### docker-compose

```bash
docker-compose stop
```

```bash
docker-compose down
```

```bash
docker-compose exec --user root ros2 bash
```

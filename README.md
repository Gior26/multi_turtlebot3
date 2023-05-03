# TurtleBot3
<img src="https://github.com/ROBOTIS-GIT/emanual/blob/master/assets/images/platform/turtlebot3/logo_turtlebot3.png" width="300">


[![humble-devel Status](https://github.com/ROBOTIS-GIT/turtlebot3/workflows/humble-devel/badge.svg)](https://github.com/ROBOTIS-GIT/turtlebot3/tree/humble-devel)

## ROBOTIS e-Manual for TurtleBot3
- [ROBOTIS e-Manual for TurtleBot3](http://turtlebot3.robotis.com/)

## Wiki for turtlebot3 Packages
- http://wiki.ros.org/turtlebot3 (metapackage)
- http://wiki.ros.org/turtlebot3_bringup
- http://wiki.ros.org/turtlebot3_description
- http://wiki.ros.org/turtlebot3_example
- http://wiki.ros.org/turtlebot3_navigation
- http://wiki.ros.org/turtlebot3_slam
- http://wiki.ros.org/turtlebot3_teleop

## Build from sources

```bash
mkdir -p turtlebot3/src
cd turtlebot3/src
git clone https://github.com/Gior26/multi_turtlebot3.git -b humble-devel
vcs import . < multi_turtlebot3/turtlebot3.repos
cd ..
rosdep install --from-paths src -y --ignore-src
colcon build --parallel-workers 1 --event-handlers console_direct+ --symlink-install
```

## Execute the simulation

```bash
source install/local_setup.bash
ros2 launch turtlebot3_gazebo turtlebot3_library.launch.py
ros2 run turtlebot3_teleop turtlebot3_teleop tb3_1
ros2 run turtlebot3_teleop turtlebot3_teleop tb3_2
ros2 run turtlebot3_teleop turtlebot3_teleop tb3_3
```

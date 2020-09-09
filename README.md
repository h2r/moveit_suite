We use OMPL 1.5 to save the PRM, and therefore install ROS Kinetic MoveIt from source. This package contains MoveIt and its dependencies, as well as OMPL 1.5.

MoveIt's kinetic-devel was checked out on 09/08/2020 using instructions here: https://moveit.ros.org/install/source/

```
wstool init src
wstool merge -t src https://raw.githubusercontent.com/ros-planning/moveit/${ROS_DISTRO}-devel/moveit.rosinstall
wstool update -t src
rosdep install -y --from-paths src --ignore-src --rosdistro ${ROS_DISTRO}
catkin config --extend /opt/ros/${ROS_DISTRO} --cmake-args -DCMAKE_BUILD_TYPE=Release
catkin build
```

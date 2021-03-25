**NOTE: This fork has slight variations from the original one.**

# Getting Started
## Installation

This package is intended to be used with Ubuntu 18.04 and [ROS kinetic](http://wiki.ros.org/melodic/Installation/Ubuntu) or above.
After installing ROS, install some extra dependencies, substituting kinetic for your ROS version as necessary:
```
sudo apt-get install ros-melodic-cmake-modules python-wstool python-catkin-tools libyaml-cpp-dev protobuf-compiler autoconf
sudo apt-get install ros-melodic-ompl libompl-dev
```
Then if not already done so, set up a new catkin workspace:
```
mkdir -p ~/catkin_ws/src
cd ~/catkin_ws
catkin init
catkin config --extend /opt/ros/kinetic
catkin config --cmake-args -DCMAKE_BUILD_TYPE=Release
catkin config --merge-devel
```
If using [**SSH keys for github**](https://help.github.com/articles/connecting-to-github-with-ssh/) (recommended):
```
cd ~/catkin_ws/src/
git clone git@github.com:ethz-asl/mav_voxblox_planning.git
wstool init . ./mav_voxblox_planning/install/install_ssh.rosinstall
wstool update
```

If **not using SSH** keys but using https instead:
```
cd ~/catkin_ws/src/
git clone https://github.com/edwinpha/mav_voxblox_planning.git
wstool init . ./mav_voxblox_planning/install/install_https.rosinstall
wstool update
```

If you have already initalized wstool replace the above `wstool init` with `wstool merge -t`

Compile:
```
cd ~/catkin_ws/src/
catkin build mav_voxblox_planning
```

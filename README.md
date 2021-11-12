dvs240 ros for xavier nx board
=============

## Installation

1. Install ROS dependencies:
```
sudo apt-get install ros-melodic-camera-info-manager
sudo apt-get install ros-melodic-image-view
```

2. Install libcaer (add required repositories as per [iniVation documentation](https://inivation.gitlab.io/dv/dv-docs/docs/getting-started.html#ubuntu-linux) first):
```
sudo apt-get install libcaer-dev
```

3. Install catkin tools:
```
sudo apt-get install python-catkin-tools
```

4. Clone the package into your catkin workspace:
```
mkdir catkin_ws_dvs240
cd catkin_ws_dvs240
mkdir src
cd src
git clone https://github.com/ziimiin14/vrpn_dvs_cm_ros.git
cd vrpn_dvs_cm_ros
git submodule init
git submodule update
cd ~/catkin_ws_dvs240

# catkin init config your workspace. Must be done
catkin config --init --mkdirs --extend /opt/ros/melodic --merge-devel --cmake-args -DCMAKE_BUILD_TYPE=Release

# Build davis_ros_driver
catkin build davis_ros_driver

# Build cm_ros
catkin build cm_ros

# Source the setup bash scripts
source devel/setup.bash
```

## Run

### cm_ros 

This package contains a [launch file](https://github.com/ziimiin14/cm_ros/blob/651bc7e6c9ffbae166ea05ad6aa39727e53f3405/launch/sample.launch) to run dvs240 event camera ros node and cm ros node.

To start:
```
roslaunch cm_ros sample.launch
```

P/S: If you want to run the dvs240 event camera ros node only, you can comment out the cm ros node specified in the [launch file](https://github.com/ziimiin14/cm_ros/blob/651bc7e6c9ffbae166ea05ad6aa39727e53f3405/launch/sample.launch).



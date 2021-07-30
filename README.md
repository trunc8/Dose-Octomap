# Dose Octomap

### Pre-requisites
- ROS Melodic installation with Gazebo9
- Packages installed: `ros-melodic-turtlebot3-*`
- ROS workspace at home directory: `~/catkin_ws`

### Demo
![Dose Octomap Demo](dose-octomap-demo.gif)

### Steps to Replicate

##### Setting up ROS Packages
```sh
cd ~/catkin_ws/src
git clone git@github.com:trunc8/Dose-Octomap.git
cd Dose-Octomap/octomap_server
rosdep install --from-paths . --ignore-src --rosdistro melodic -y
cd ~/catkin_ws
catkin build -j3
```

##### Octomap Library
```sh
cd ~
git clone -b library git@github.com:trunc8/Dose-Octomap.git
cd Dose-Octomap/octomap/
mkdir build && cd build
cmake ..
sudo make install
sudo cp ../lib/liboctomap.* /opt/ros/melodic/lib/
```

##### Running the demonstration
```sh
### Optional steps commented below
### You should ideally have these in your .bashrc or .zshrc
# export TURTLEBOT3_MODEL=waffle
# source /opt/ros/melodic/setup.sh
# source ~/catkin_ws/devel/setup.sh
roslaunch demonstrations dose_octomap_demo.launch paused:=True
```

### Author(s)

* **Siddharth Saha** - [trunc8](https://github.com/trunc8)
* [octomap Library](https://github.com/OctoMap/octomap)
* [octomap_mapping ROS Package](https://github.com/OctoMap/octomap_mapping)

### Acknowledgement

* Prof. Leena Vacchani

<p align='center'>Created with :heart: by <a href="https://www.linkedin.com/in/sahasiddharth611/">Siddharth</a></p>
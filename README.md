# gazebo_velodyne_slam

![Screenshot from 2021-04-18 01-46-43](https://user-images.githubusercontent.com/7419790/115120353-fb75df80-9fe7-11eb-98bb-68dc55578f34.png)

``` sh
# install octomap ros
sudo apt-get install ros-melodic-octomap
sudo apt-get install ros-melodic-octomap-server

# clone turtlebot3

git clone https://github.com/ROBOTIS-GIT/turtlebot3
git clone https://github.com/ROBOTIS-GIT/turtlebot3_msgs
git clone https://github.com/ROBOTIS-GIT/turtlebot3_simulations


# clone velodyne simulator
git clone https://github.com/lmark1/velodyne_simulator

# clone this repository
git clone https://github.com/Hyun-je/gazebo_velodyne_slam

# install cartographer_ros
sudo apt-get update
sudo apt-get install -y python-wstool python-rosdep ninja-build stow

cd catkin_ws
wstool init src
wstool merge -t src https://raw.githubusercontent.com/cartographer-project/cartographer_ros/master/cartographer_ros.rosinstall
wstool update -t src

sudo rosdep init
rosdep update
rosdep install --from-paths src --ignore-src --rosdistro=${ROS_DISTRO} -y

src/cartographer/scripts/install_abseil.sh

sudo apt-get remove ros-${ROS_DISTRO}-abseil-cpp


# build
catkin_make_isolated --install --use-ninja
```

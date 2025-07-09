git clone https://github.com/dave601601/PX4-VTOL.git --recursive
bash ./PX4-VTOL/Tools/setup/ubuntu.sh
reboot


cd {this repo root}
DONT_RUN=1 make px4_sitl_default gazebo-classic_standard_vtol
source {catkin ws root}/devel/setup.bash   
source Tools/simulation/gazebo-classic/setup_gazebo.bash $(pwd) $(pwd)/build/px4_sitl_default
export ROS_PACKAGE_PATH=$ROS_PACKAGE_PATH:$(pwd)
export ROS_PACKAGE_PATH=$ROS_PACKAGE_PATH:$(pwd)/Tools/simulation/gazebo-classic/sitl_gazebo-classic
roslaunch px4 posix_sitl.launch vehicle:=vtolcam

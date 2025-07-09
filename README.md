
No hanguel keyboard in my ubuntu. sorry


##  Setup


   
```bash
git clone https://github.com/dave601601/PX4-VTOL.git --recursive
bash ./PX4-VTOL/Tools/setup/ubuntu.sh
reboot
```



---

## Run

change {this_repo_root} and {catkin_ws_root}

```bash
cd {this repo root}
DONT_RUN=1 make px4_sitl_default gazebo-classic_standard_vtol
source {catkin_ws_root}/devel/setup.bash   
source Tools/simulation/gazebo-classic/setup_gazebo.bash $(pwd) $(pwd)/build/px4_sitl_default
export ROS_PACKAGE_PATH=$ROS_PACKAGE_PATH:$(pwd)
export ROS_PACKAGE_PATH=$ROS_PACKAGE_PATH:$(pwd)/Tools/simulation/gazebo-classic/sitl_gazebo-classic
roslaunch px4 posix_sitl.launch vehicle:=vtolcam
```
  


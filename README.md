# Democar (This package is for ros2 foxy)


* Create a ros2 workspace

```
mkdir -p ~/ros2_ws/src
cd ~/ros2_ws/src
```

* Download the democar package into src directory

```
git clone -b master git@github.com:changwoo0224/democar.git
```

Change permission of setup.sh and install
```
chmod 777 setup.sh
./setup.sh
```
* Build the package and soruce
```
cd ~/ros2_ws/
colcon build --symlink-install --packages-select democar_gazebo
colcon build --symlink-install --packages-select democar_controller
colcon build --symlink-install --packages-select democar_odom
colcon build --symlink-install --packages-select democar_slam
colcon build --symlink-install --packages-select democar_navigation
source install/setup.bash
```

* Run Gazebo

```
ros2 launch democar_gazebo empty_world.launch.py
ros2 launch democar_gazebo racecourse.launch.py
```

![example](https://github.com/user-attachments/assets/331b91b5-7aed-4daf-853e-b9f4cfd4c861)

* Run the SLAM tool box

```
ros2 launch democar_gazebo racecourse.launch.py
ros2 launch democar_slam slam_toolbox.launch.py
```
"Be sure that first code and second must run diferent terminal window"

* Run the navigation

```
ros2 launch democar_gazebo racecourse.launch.py
ros2 launch democar_navigation racecourse_bringup_launch.py
```
"Make sure that the first command and the second command are run in different terminal windows."
"You can change map file"


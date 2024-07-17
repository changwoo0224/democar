# Democar (This package is for ros2 foxy)


* Make ros2 work space

```
mkdir -p ~/ros2_ws/src
cd ~/ros2_ws/src
```

* Download democar package to src

```
git clone -b master git@github.com:changwoo0224/democar.git
```

Change permission of setup.sh and install
```
chmod 777 setup.sh
./setup.sh
```
* build package and soruce
```
cd ~/ros2_ws/
colcon build --symlink-install --packages-select democar_gazebo
colcon build --symlink-install --packages-select democar_controller
colcon build --symlink-install --packages-select democar_odom
colcon build --symlink-install --packages-select democar_slam
colcon build --symlink-install --packages-select democar_navigation
source install/setup.bash
```

* run Gazebo

```
ros2 launch democar_gazebo empty_world.launch.py
ros2 launch democar_gazebo racecourse.launch.py
```

![example](https://github.com/user-attachments/assets/331b91b5-7aed-4daf-853e-b9f4cfd4c861)

* run slam tool box

```
ros2 launch democar_gazebo racecourse.launch.py
ros2 launch democar_slam slam_toolbox.launch.py
```
"Be sure that first code and second must run diferent terminal window"

* run naviation

```
ros2 launch democar_gazebo racecourse.launch.py
ros2 launch democar_navigation racecourse_bringup_launch.py
```
"Be sure that first code and second must run diferent terminal window"
"You can change map file"


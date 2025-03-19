## MyBot

Commands:

colcon build --symlink-install
source install/setup.bash
ros2 launch diff_drive_bot_pkg sim.launch.py
ros2 control list_hardware_interfaces
ros2 run rviz2 rviz2

Joystick

sudo apt install joystick jstest-gtk evtest
evtest or jtest-gtk
ros2 run joy joy_enumerate_devices
ros2 launch diff_drive_bot_pkg joystick.launch.py

SLAM

ros2 launch slam_toolbox online_async_launch.py params_file:=./src/MyBot/config/mapper_params_online_async.yaml use_sim_time:=true

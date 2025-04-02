## MyBot

Commands:

colcon build --symlink-install
source install/setup.bash
ros2 launch diff_drive_bot_pkg sim.launch.py
ros2 control list_hardware_interfaces
ros2 run rviz2 rviz2

Teleop

sudo apt install joystick jstest-gtk evtest
evtest or jtest-gtk
ros2 run joy joy_enumerate_devices
ros2 launch diff_drive_bot_pkg joystick.launch.py

ros2 run teleop_twist_keyboard teleop_twist_keyboard

SLAM

ros2 launch slam_toolbox online_async_launch.py params_file:=./src/MyBot/config/mapper_params_online_async.yaml use_sim_time:=true

Twist Mux

ros2 run twist_mux twist_mux --ros-args --params-file ./config/twist_mux.yaml -r cmd_vel_out:=diff_cont/cmd_vel_unstamped

Nav2

ros2 launch diff_drive_bot_pkg localization_launch.py map:=./my_map_save.yaml use_sim_time:=true
ros2 launch diff_drive_bot_pkg navigation_launch.py use_sim_time:=true subscribe_transient_local:=true

FoxGlove

ros2 launch foxglove_bridge foxglove_bridge_launch.xml


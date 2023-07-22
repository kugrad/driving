>>SLAM
roslaunch turtlebot3_gazebo turtlebot3_world.launch
roslaunch turtlebot3_slam turtlebot3_slam.launch slam_mathod:=gmapping
roslaunch turtlebot3_teleop turtlebot3_teleop_key.launch
rosrun map_server map_saver -f ~/map

>>NAVIGATION
roslaunch turtlebot3_gazebo turtlebot3_world.launch [hwi_gazebo]
roslaunch turtlebot3_navigation turtlebot3_navigation.launch map_file:=$HOME/map.yaml [hwi_rviz]
(You should use '2D Pose Estimate' in Rviz to match the map)
rosrun move_turtlebot move_turtlebot.py [hwi_move]

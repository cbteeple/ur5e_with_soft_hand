# ur5e_with_soft_hand
My custom setup of a UR5e with a soft hand placeholder.

This is a working URDF + MoveIt! config for my system, with a placeholder box for my soft hand. This is a conservative estimate for planning purposes, but also include the mass of the hand. I followed an [excellent tutorial](https://gramaziokohler.github.io/compas_fab/latest/examples/03_backends_ros/07_ros_create_urdf_ur5_with_measurement_tool.html)

## Update the URDF
To update the URDFs, edit the "**.xacro**" files inside the "_ur5e_with_soft_hand_" folder, then run:
```bash
rosrun xacro xacro -o ur5e_with_soft_hand.urdf ur5e_with_soft_hand.xacro
```

Then you can view changes in the rviz viewer:
```bash
roslaunch ur5e_with_soft_hand display.launch
```

## This was generated using the setup assistent
```bash
roslaunch moveit_setup_assistant setup_assistant.launch
```

## Use this for motion planning on the real arm
```bash
roslaunch ur5e_with_soft_hand_moveit_config ur5e_with_soft_hand_moveit_planning_execution.launch limited:=false &

roslaunch ur5e_with_soft_hand_moveit_config moveit_rviz_2.launch config:=true
```

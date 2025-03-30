## Interacting with Topics
(We assume that you have already installed the Waver simulation and the required dependencies. If not, please refer to the [Installation Guide](../00_installation/README.md) for instructions.)

In this section, you will interact with the Waver topics.

Let's start in the `ROS2_Docker_UI` with VSCode. Enter to the container and build the workspace:
```bash
./scripts/run
```

Then build the workspace:
```bash
colcon build
```

Execute the ROS2 simulation:
```bash
ros2 launch waver_description view_gazebo.launch.py
```

Now open a new terminal and enter to the container:
```bash
./scripts/bash
## once inside the container
source /ros2_ws/install/setup.bash
```

Use the following command to list the topics:
```bash
ros2 topic list
```

You should see a list of topics similar to the following:
```
/camera/camera_info
/camera/image_raw
/camera/image_raw/compressed
/camera/image_raw/compressedDepth
/camera/image_raw/theora
/clicked_point
/clock
/cmd_vel
/gazebo/link_states
/gazebo/model_states
/goal_pose
/imu/data
/initialpose
/joint_states
/odom
/parameter_events
/performance_metrics
/robot_description
/rosout
/scan
/tf
/tf_static
```

Get the information of a specific topic:
```bash
ros2 topic info /camera/image_raw
```

You should see a result similar to the following:
```
Type: sensor_msgs/msg/Image
Publisher count: 1
Subscription count: 1
```

Also you can see the type of the message:
```bash
ros2 topic type /camera/image_raw
```

You should see a result similar to the following:
```
sensor_msgs/msg/Image
```

Now you can see the message type. To print the message, use the following command:
```bash
ros2 topic echo /imu/data
```

Do the same for:
- `/cmd_vel`
- `/scan`

Let's create a custom rviz configuration to visualize the topics. 

Open RVIZ
```bash
rviz2
```

In the RVIZ window, click on the "Add" button in the bottom left corner. This will open a dialog where you can select the type of visualization you want to add.

![](.media/custom_rviz.png)

Once you add the topics to RVIZ2, you can see the data in the RVIZ2 window. You can also change the properties of each visualization by selecting it in the left panel and modifying the properties in the right panel.

You can also save the configuration by clicking on `File` -> `Save Config As...` and choosing a location to save the configuration file. This way, you can load it later by clicking on `File` -> `Open Config...` and selecting the saved configuration file. We suggest for now, save the configuration in the `ros2_ws` package. 

To validate the rviz configuration, you can open with the following command:
```bash
ros2 run rviz2 rviz2 -d <rviz_config_file>
```


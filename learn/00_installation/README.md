# Installation

For this project, we will use Docker to create a container with all the dependencies needed for the project. This way, we can avoid installing all the dependencies on our local machine and reduce the amount of issues related with the installation process.

Also make sure you have:
- VSCode
- Git

## Windows
(Pending to document)

## Ubuntu
We suggest install docker via script as you can found at [Docker website](https://docs.docker.com/engine/install/ubuntu/):
```
curl -fsSL https://get.docker.com -o get-docker.sh
sudo sh get-docker.sh
```

## Mac OS
(Pending to document)

## Workspace based on Docker

### 1. Clone the Docker_UI repository
```
git clone https://github.com/aldajo92/ROS2_Docker_UI.git
```

### 2. Move to the ros2_ws/src directory
```
cd ROS2_Docker_UI/ros2_ws/src
```

or using vscode:
```
code ROS2_Docker_UI
```

Once VSCode is open, you can open a terminal and run the command:
```
cd ros2_ws/src
```

### 3. Clone the Waver repositories in the ros2_ws/src directory
```
git clone https://github.com/aldajo92/waver_description_ros2.git
git clone https://github.com/aldajo92/waver_cv_ros2.git
git clone https://github.com/aldajo92/waver_bringup_ros2.git
```

### 4. Build the Docker image
Move tho the Docker_UI directory:
```
cd ../..
```

Then build the Docker image:
```
./scripts/build
```

### 5. Run the Docker container
```
./scripts/run
```

Then you will be in the Docker container terminal. It will be open by default in the `ros2_ws` directory. Then build the workspace:
```
colcon build
```


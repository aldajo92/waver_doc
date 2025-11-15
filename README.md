# Waver (Wavershare Rover) Documentation ROS2

This repository contains the documentation for the Waver project.

## Table of Contents

- [Hardware Setup](In progress)
- [Software Setup](In progress)
- [ROS2 Simulation]

## Hardware Setup

Install a raspberry pi image in a sdcard using [imager](https://www.raspberrypi.com/software/).
- user recommended : `robot`
- hostname recommended : `waverbot01`

Connect via ssh: `ssh robot@waverbot01.local`

Once connected to the OS via ssh, install docker using the [script method](https://docs.docker.com/engine/install/ubuntu/#install-using-the-convenience-script):

```bash
curl -fsSL https://get.docker.com -o get-docker.sh
sudo sh get-docker.sh
```

Then use the [linux-post install setup](https://docs.docker.com/engine/install/linux-postinstall/):
```bash
sudo groupadd docker
sudo usermod -aG docker $USER
newgrp docker
docker run hello-world
```

Then make sure to enable i2c and VNC using `raspiconfig`:

```bash
sudo raspi-config
# Go to: "Interface Option" -> I2C -> Enable I2C
# Go to: "Interface Option" -> VNC -> Enable VNC
```


## Software Setup
(Section in progress)

## ROS2 Simulation

The ROS2 simulation for the Waver project is divided into the following repositories:

[Docker container for ROS2 development](https://github.com/aldajo92/ROS2_Docker_UI)

ROS2 Dependencies:
- [Waver Description](https://github.com/aldajo92/waver_description_ros2)
- [Waver CV](https://github.com/aldajo92/waver_cv_ros2)
- [Waver Bringup](https://github.com/aldajo92/waver_bringup_ros2)

Some useful videos about Waver simulation:
- [Map Creation](https://youtu.be/AoRMaDEAwi0)
- [Localization](https://youtu.be/lmo4bQItBuc)
- [Navigation](https://youtu.be/TQU_-gRvsCE)

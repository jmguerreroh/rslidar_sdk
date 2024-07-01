# **rslidar_sdk**

This project has been modified to use the RoboSense Lidar with ROS2


## 1. Introduction

**rslidar_sdk** is the Software Development Kit of the RoboSense Lidar based on Ubuntu. It contains:

+ The lidar driver core [rs_driver](https://github.com/RoboSense-LiDAR/rs_driver),
+ The ROS support, 
+ The ROS2 support,

To get the point cloud through ROS/ROS2, please just use this SDK. 

To integrate the Lidar driver into your projects, please use the rs_driver.

### 1.1. LiDAR Supported

- RS-LiDAR-16
- RS-LiDAR-32
- RS-Bpearl
- RS-Helios
- RS-Helios-16P
- RS-Ruby-128
- RS-Ruby-80
- RS-Ruby-48
- RS-Ruby-Plus-128
- RS-Ruby-Plus-80
- RS-Ruby-Plus-48
- RS-LiDAR-M1
- RS-LiDAR-M2
- RS-LiDAR-E1

### 1.2. Point Type Supported

- XYZI - x, y, z, intensity
- XYZIRT - x, y, z, intensity, ring, timestamp


## 2. Download via Git

Download the rslidar_sdk as below. 

```sh
mkdir -p ~/rslidar_ws/src
cd ~/rslidar_ws/src
git clone https://github.com/jmguerreroh/rslidar_sdk.git
```


## 3. Dependencies

### 3.1. ROS2

To use rslidar_sdk in the ROS2 environment, please install the below libraries.
+ Ubuntu 22.04 - ROS2 Humble desktop

For installation, please refer to https://docs.ros.org/en/humble/Installation.html

### 3.2. Yaml (Essential) 

version: >= v0.5.2

*If ros-distro-desktop-full is installed, this step can be skipped*

Installation:

```sh
sudo apt-get update
sudo apt-get install -y libyaml-cpp-dev
```

### 3.3. libpcap (Essential) 

version: >= v1.7.4

Installation:

```sh
sudo apt-get install -y  libpcap-dev
```


## 4. Compile & Run with ROS2 colcon

Configure your IP address to 192.168.1.102

Execute:
```sh
cd ~/rslidar_ws/src
vcs import < rslidar_sdk/thirdparty.repos
cd ~/rslidar_ws
colcon build --symlink-install
source install/setup.bash
ros2 launch rslidar_sdk start.launch.py
```


## 5. Introduction to parameters

To change the behaviors of rslidar_sdk, change its parameters. please read the following links for detailed information.

[Intro to parameters](doc/intro/02_parameter_intro.md)

[Intro to hidden parameters](doc/intro/03_hiding_parameters_intro.md)


## 6. Quick start

Below are some quick guides to use rslidar_sdk. 

[Connect to online LiDAR and send point cloud through ROS](doc/howto/06_how_to_decode_online_lidar.md)

[Decode PCAP file and send point cloud through ROS](doc/howto/08_how_to_decode_pcap_file.md)

[Change Point Type](doc/howto/05_how_to_change_point_type.md) 


## 7. Advanced Topics

[Online Lidar - Advanced topics](doc/howto/07_online_lidar_advanced_topics.md) 

[PCAP file - Advanced topics](doc/howto/09_pcap_file_advanced_topics.md) 

[Coordinate Transformation](doc/howto/10_how_to_use_coordinate_transformation.md) 

[Record rosbag & Replay it](doc/howto/11_how_to_record_replay_packet_rosbag.md)




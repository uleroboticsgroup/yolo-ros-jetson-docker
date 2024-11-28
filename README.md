<h1 align="center"> YOLO and ROS for Jetson Nano Ubuntu 20.04 Docker Images </h1>

## What is this?

Hardware-accelerated PyTorch on Ubuntu 20.04 for deploying [yolo_ros](https://github.com/mgonzs13/yolo_ros) with ROS 2 (Humble) and Python 3.8.

## How to use

To run the docker with the nvidia dependencies, it is neccesary to install the [NVIDIA Container Toolkit](https://docs.nvidia.com/datacenter/cloud-native/container-toolkit/latest/install-guide.html) and to configure Docker to recognize the container toolkit.

To run the container:

```sh
docker run -it --rm --ipc=host --runtime=nvidia --network=host --privileged <image> bash
```

At `~/ros2_ws`, it is installed the `yolo_ros` package with its dependecies. Using bash, this workspace and the humble workspace will be sourced. To launch the package, you can launch:

```sh
ros2 launch yolo_bringup yolov11.launch.py
```

## Pulling existing images

<div style="width:100%;">

| Python Version | Dockerhub Image Name                     | Size    |
|----------------|------------------------------------------|---------|
| `Python3.8`    | `agonzc34/yolo-ros:humble-l4t-r32.7.1`   | 16.8 GB |

</div>

> **note:** Make sure to run the container on the latest L4T host system (r32.7.1). Running on older JetPack releases (e.g. r32.6.1) can cause driver issues, since L4T drivers are passed into the container

> This image based on the [Jetson_Ubuntu20_Images](https://github.com/timongentzsch/Jetson_Ubuntu20_Images)

## References

- [jetson_nano_ubuntu20_docker](https://github.com/jayfalls/jetson_nano_ubuntu20_docker/tree/main)
- [Jetson_Ubuntu20_Images](https://github.com/timongentzsch/Jetson_Ubuntu20_Images)
- [yolo_ros](https://github.com/mgonzs13/yolo_ros)
- [GitHub](https://github.com/uleroboticsgroup/yolo-ros-jetson-docker)
- [Docker Hub](https://hub.docker.com/repository/docker/agonzc34/yolo-ros/general)
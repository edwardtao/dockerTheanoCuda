# Start with Ubuntu base image
FROM ubuntu:16.04
MAINTAINER Kai Arulkumaran <design@kaixhin.com>

# Install wget and lsb-release
RUN apt-get update && apt-get install -y wget lsb-release
# Set up sources and keys
RUN echo "deb http://packages.ros.org/ros/ubuntu $(lsb_release -sc) main" > /etc/apt/sources.list.d/ros-latest.list && \
  apt-key adv --keyserver hkp://pool.sks-keyservers.net --recv-key 0xB01FA116
# Install ROS base with rosinstall
RUN apt-get update && apt-get install -y \
  ros-kinetic-ros-base \
  python-rosinstall
# Initialise rosdep
RUN rosdep init && rosdep update
# Set up environment
RUN echo "source /opt/ros/kinetic/setup.bash" >> ~/.bashrc

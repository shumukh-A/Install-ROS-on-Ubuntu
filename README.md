# Install-ROS-on-Ubuntu
## 1: Download Ubuntu 20.04.4 LTS (Focal Fossa)
click on 64-bit PC (AMD64) desktop image

https://releases.ubuntu.com/focal/

## 2: Download VirtualBox
click on Windows hosts 

https://www.virtualbox.org/wiki/Downloads

## 3: Ubuntu install of ROS Noetic
open the terminal and Write sequentially the following codes 

#### 1- Setup your sources.list
Setup your computer to accept software from packages.ros.org.
```
sudo sh -c 'echo "deb http://packages.ros.org/ros/ubuntu $(lsb_release -sc) main" > /etc/apt/sources.list.d/ros-latest.list'
```
Mirrors Source Debs are also available
#### 2- Set up your keys
```
sudo apt install curl # if you haven't already installed curl
curl -s https://raw.githubusercontent.com/ros/rosdistro/master/ros.asc | sudo apt-key add -
```
#### 3-Installation
First, make sure your Debian package index is up-to-date:
```
sudo apt update
```
Now pick how much of ROS you would like to install.

Desktop-Full Install: (Recommended) : Everything in Desktop plus 2D/3D simulators and 2D/3D perception packages
```
sudo apt install ros-noetic-desktop-full
```
#### 4- Environment setup
You must source this script in every bash terminal you use ROS in.

It can be convenient to automatically source this script every time a new shell is launched. These commands will do that for you.

Bash
```
echo "source /opt/ros/noetic/setup.bash" >> ~/.bashrc
source ~/.bashrc
```
#### 5- Dependencies for building packages
Up to now you have installed what you need to run the core ROS packages. To create and manage your own ROS workspaces, there are various tools and requirements that are distributed separately. For example, rosinstall is a frequently used command-line tool that enables you to easily download many source trees for ROS packages with one command.

To install this tool and other dependencies for building ROS packages, run:
```
sudo apt install python3-rosdep python3-rosinstall python3-rosinstall-generator python3-wstool build-essential
```
#### 6- Initialize rosdep
Before you can use many ROS tools, you will need to initialize rosdep. rosdep enables you to easily install system dependencies for source you want to compile and is required to run some core components in ROS. If you have not yet installed rosdep, do so as follows.
```
sudo apt install python3-rosdep
```
With the following, you can initialize rosdep.
```
sudo rosdep init
rosdep update
```
#### 7- To start the ROS
```
roscore
```
![6E32883C-D0DE-4943-AD13-1442964EE947](https://github.com/user-attachments/assets/92dc3fb0-b26b-4b9b-a3bc-a07569d0c38d)

http://wiki.ros.org/noetic/Installation/Ubuntu


# Task 2: Install Ros into Jetson nano

This file will represent the steps to install Robot Operating System (ROS) into Jetson nano.



 
## Installation steps

#### 1. Set locale
Make sure that we have locale supports UTF-8

```bash
locale  
```

```bash
sudo apt update && sudo apt install locales 
```

```bash
sudo locale-gen en_US en_US.UTF-8  
```

```bash
sudo update-locale LC_ALL=en_US.UTF-8 LANG=en_US.UTF-8  
```

```bash
export LANG=en_US.UTF-8  
```


#### 2. Setup the sources
```bash
apt-cache policy | grep universe
```

#### 3. Enable the Universe repository with the instructions.
```bash 
sudo apt install software-properties-common
```

```bash 
sudo add-apt-repository universe
```

#### 4. Add ROS2 repository to the system
```bash 
sudo apt update && sudo apt install curl gnupg2 lsb-release
```
```bash
sudo curl -sSL https://raw.githubusercontent.com/ros/rosdistro/master/ros.key  -o /usr/share/keyrings/ros-archive-keyring.gpg
```


#### 5. Add the repository to the sources list
```bash
echo "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/ros-archive-keyring.gpg] http://packages.ros.org/ros2/ubuntu $(source /etc/os-release && echo $UBUNTU_CODENAME) main" | sudo tee /etc/apt/sources.list.d/ros2.list > /dev/null
```

#### 6. Install ROS 2 packages
update the apt repository
```bash
sudo apt update
```
upgrade 
```bash
sudo apt upgrade
```
- Desktop Install: ROS, RViz, demos, tutorials.
```bash
sudo apt install ros-foxy-desktop
```
- ROS-Base Install (Bare Bones): Communication libraries, message packages, command line tools. No GUI tools.
```bash
sudo apt install ros-foxy-ros-base
```
##### 7. Setup the enviroment
- Bash 
```bash
echo "source /opt/ros/foxy/setup.bash" >> ~/.bashrc
source ~/.bashrc
```
- Zsh
```bash
echo "source /opt/ros/foxy/setup.zsh" >> ~/.zshrc
source ~/.zshrc
```


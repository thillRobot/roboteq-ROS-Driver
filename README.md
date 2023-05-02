#roboteq-ROS-Driver (forked from Roboteq-Inc/ROS-Driver)
forked by thillRobot

this is a ROS packge for the Roboteq motor driver 
tested with driver model SDC2160, ROS Noetic, Ubuntu 20.04 (x86_64)

## catkin build environment
this package is built with `catkin build`

## python environment
the python environment is managed with venv

run the following to activate venv
```
source ~/.venv/roboteq-build-env/bin/activate
```

upgrade pip and install the following python packages

```
pip install --upgrade pip
```

```
pip install wheel empy rospkg
```

## ROS noetic 
install ros following standard instructions, choose `desktop-full`
addittional package is required for USB serial communication

```
sudo apt update
sudo apt install ros-noetic-serial
```

## configure the ros workspace

```
mkdir -p catkin_build_ws/src
cd catkin_build_ws
catkin build
```

## install this package (a fork of Roboteq-inc/ROS-Driver)

```

cd catkin_build_ws/src
git clone git@github.com:thillRobot/roboteq-ROS-Driver
cd .. 
catkin build
```

## install teleop_twist_keyboard (or use `apt install`)
```
cd catkin_build_ws/src
git clone https://github.com/ros-teleop/teleop_twist_keyboard.git
```

## differential steer kinematics

the kinematic equations for a standard diff steer robot have been added to `roboteq_motor_controller_driver_node.cpp`
see lines 99-119


turn on the motor controller node using diff steer kinematics
```
roslaunch roboteq_motor_controller_driver driver.launch
```

drive the robot with keyboard drive
```
rosrun teleop_twist_keyboard teleop_twist_keyboard.py
```

watch the magic





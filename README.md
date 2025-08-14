# 🐢 ROS 2 Humble – Turtlesim Manipulation Guide

## 📌 Overview
This project demonstrates how to install, run, and manipulate the **Turtlesim** package in **ROS 2 Humble**.  
It includes step-by-step commands, explanations, and examples to help you practice ROS concepts.

---

## 📦 1. Install Turtlesim
```bash
sudo apt update
sudo apt install ros-humble-turtlesim
```
Installs the **Turtlesim** simulator package.

---

## 🔧 2. Source ROS 2 Environment
Every time you open a new terminal:
```bash
source /opt/ros/humble/setup.bash
```
Make it permanent:
```bash
echo "source /opt/ros/humble/setup.bash" >> ~/.bashrc
source ~/.bashrc
```

---

## ▶️ 3. Run Turtlesim
**Terminal 1 – Start Turtlesim Node**
```bash
ros2 run turtlesim turtlesim_node
```
**Terminal 2 – Control with Keyboard**
```bash
ros2 run turtlesim turtle_teleop_key
```

---

## 📡 4. View Available Topics
```bash
ros2 topic list
```
Example output:
```
/turtle1/cmd_vel
/turtle1/pose
/rosout
/parameter_events
```

---

## 🚀 5. Move Turtle Programmatically
```bash
ros2 topic pub /turtle1/cmd_vel geometry_msgs/Twist "{linear: {x: 2.0}, angular: {z: 1.8}}"
```
Moves the turtle forward and turns at the same time.

---

## 🐢 6. Spawn a New Turtle
```bash
ros2 service call /spawn turtlesim/srv/Spawn "{x: 5.0, y: 5.0, theta: 0.0, name: 'turtle2'}"
```
Spawns a second turtle at coordinates (5, 5).

---

## 🎨 7. Change Background Color
```bash
ros2 param set /turtlesim background_r 200
ros2 param set /turtlesim background_g 200
ros2 param set /turtlesim background_b 255
ros2 service call /clear std_srvs/srv/Empty
```
Changes the simulation background to light blue.

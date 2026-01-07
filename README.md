# 🛡️ Border Surveillance Detection Drone System

This project simulates a border surveillance and detection drone system aimed at improving security and situational awareness in restricted border areas. Autonomous drones patrol predefined zones, detect suspicious activities, and provide real-time alerts to operators through a monitoring system.

---

## 📌 Project Overview

The **Border Surveillance Detection Drone System** is a fully simulated autonomous UAV platform designed for border monitoring scenarios.  
It integrates flight control, perception, and mission logic to demonstrate how a surveillance drone can patrol, detect thermal targets, and react autonomously.

This project is intended for **research, education, and prototyping** and can be extended toward real-world deployment.

---

## 🎯 Objectives

- Detect and monitor **smuggling attempts** by individuals, vehicles, or any object that emits heat using thermal imaging  
- Perform **autonomous drone patrols** along predefined GPS-based border routes  
- Conduct **inspection and investigation maneuvers** (hovering, orbiting, close-range observation) before border guard or human intervention  
- Integrate **PX4 flight control** with **ROS 2–based perception and sensor processing pipelines**  
- Simulate **realistic border surveillance scenarios**, including night operations and low-visibility conditions  
- Enable **early threat detection and situational awareness** to reduce human risk and response time  

---

## 🧠 System Architecture


![Uploading image.png…]()

---

## 🛠️ Technologies Used

### Flight & Simulation
- PX4 Autopilot (SITL)
- Gazebo / GZ Simulator
- x500_gimbal drone model

### Middleware & Control
- MAVLink
- MAVSDK (Python + MAVSDK Server)

### Robotics & Perception
- ROS 2 Humble
- ros_gz_bridge
- RViz2
- Thermal camera sensor

---

## 🌍 Simulation Environment

### World
- Custom Gazebo world representing a border environment
- Includes terrain, human models, and rocket-like objects

### Thermal Properties

Thermal targets are simulated using temperature values.

**Human model**
``xml
&lt;thermal&gt;
  &lt;temperature&gt;310&lt;/temperature&gt;
&lt;/thermal&gt;
---

##Drone Capabilities

-Autonomous takeoff and landing

-Waypoint navigation

-Orbiting and inspecting detected targets

-Gimbal-stabilized thermal camera

-Automatic Return-To-Launch (RTL)
---

## Thermal Camera Pipeline

Gazebo Thermal Sensor
        ↓
   ros_gz_bridge
        ↓
   ROS 2 Image Topic
        ↓
   RViz2 / Processing Node

##thermal image topic

###/world/baylands/model/x500_gimbal_0/link/camera_link/sensor/thermal_camera/image
---

##Mission Logic

The drone mission follows these steps:

  1-Arm and take off to a predefined altitude

  2-Navigate to mission waypoints

  3-Descend for close inspection when reaching a target

  4-Orbit the target for surveillance

  5-Continue to the next target

  6-Return to launch automatically

  7-Mission logic is implemented using Python with MAVSDK.

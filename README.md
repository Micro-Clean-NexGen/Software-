# Software-
# MicroClean Navigation Stack

**ROS 2 Jazzy Autonomous Navigation Software for the MicroClean Autonomous Steam Cleaning Robot**

---

## Overview

MicroClean Navigation is the software stack responsible for autonomous navigation, localization, mapping, and mission execution for the MicroClean robot.

The project is currently focused on developing and validating the navigation software in simulation before deployment on the physical robot.

---

## Project Goals

- Autonomous navigation
- Environment mapping
- Robot localization
- Path planning
- Obstacle avoidance
- Waypoint navigation
- Cleaning mission execution
- Simulation-based development

---

## Technology Stack

| Component | Technology |
|-----------|------------|
| Operating System | Ubuntu 26.04 |
| Robotics Framework | ROS 2 Jazzy |
| Navigation | Nav2 |
| Mapping | SLAM Toolbox |
| Localization | AMCL |
| Simulation | Gazebo Harmonic |
| Visualization | RViz2 |
| Programming | Python / C++ |
| Containerization | Docker |

---

## Repository Structure

```
MicroClean-Navigation

├── docker/
│   ├── Dockerfile
│   ├── docker-compose.yml
│   └── entrypoint.sh
│
├── microclean_ws/
│   └── src/
│       ├── microclean_description/
│       ├── microclean_bringup/
│       ├── microclean_navigation/
│       ├── microclean_simulation/
│       └── microclean_interfaces/
│
├── maps/
├── worlds/
├── docs/
├── screenshots/
└── README.md
```

---

## System Overview

```
User
   │
   ▼
Mission Command
   │
   ▼
Mission Manager
   │
   ▼
Navigation Stack
   │
   ▼
Nav2
   │
   ▼
Robot Controller
   │
   ▼
Mobile Robot
```

---

## Navigation Pipeline

```
Sensors
   │
   ▼
SLAM Toolbox
   │
   ▼
Map
   │
   ▼
AMCL
   │
   ▼
Nav2
   │
   ▼
Controller
   │
   ▼
cmd_vel
   │
   ▼
Robot Motion
```

---

## Planned Capabilities

- Create maps
- Localize within known environments
- Navigate to target locations
- Avoid obstacles
- Execute waypoint missions
  

---

## Simulation

The project is developed and tested in simulation before hardware deployment.

Simulation includes:

- Robot model
- Indoor environments
- Navigation testing
- Mission execution
- Sensor simulation

---

## Hardware Target

The navigation software is intended to interface with the MicroClean robot platform.

Planned onboard hardware includes:

- Raspberry Pi 5
- LiDAR
- IMU
- Mobile robot base
- Motor controller
- Cleaning subsystem

> Hardware integration is under development and may evolve as the project progresses.

---

## Getting Started

### Build Docker Image

```bash
docker build \
-f docker/Dockerfile \
-t microclean_ros2 .
```

### Run Container

```bash
docker run -it \
--name microclean_robot \
microclean_ros2
```

### Build Workspace

```bash
cd /microclean_ws

colcon build

source install/setup.bash
```

### Launch Simulation

```bash
ros2 launch microclean_bringup simulation.launch.py
```

---

## Project Status

Current development focuses on:


- ROS 2 workspace
- Simulation
- Navigation stack integration

Additional functionality will be added as development progresses.

---

## Roadmap

- Navigation simulation
- Robot description
- Mapping
- Localization
- Autonomous waypoint navigation
- Cleaning mission execution
- Hardware integration

---

## Contributing

This repository is under active development.

Contributions, suggestions, and improvements are welcome.

---

## License

This project is currently under active development.

© MicroClean Robotics

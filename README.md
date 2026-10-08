# 🚗 Real-Time ADAS Collision Avoidance System

## 📌 Project Overview

The Real-Time ADAS Collision Avoidance System is an ESP32-based embedded system developed as part of the PEP Embedded Training. The project demonstrates real-time collision avoidance using sensor fusion, fault isolation, mixed-criticality scheduling, and safety supervision.

The system uses an HC-SR04 ultrasonic sensor, IR sensors, and an MPU6050 to monitor the surrounding environment and vehicle motion. Bluetooth commands from a mobile phone are used to control the four-wheel vehicle. When a dangerous obstacle condition is detected, the safety mechanism can override the normal movement command and stop the vehicle.

## 🎯 Objectives

- Develop an ESP32-based real-time ADAS prototype.
- Detect obstacles using ultrasonic and IR sensors.
- Monitor vehicle motion using the MPU6050.
- Control a four-wheel vehicle through Bluetooth.
- Combine sensor information using sensor fusion.
- Identify abnormal sensor conditions using fault isolation.
- Give higher priority to safety-related operations.
- Stop the vehicle automatically during dangerous obstacle conditions.

## 🛠️ Hardware Components

- ESP32 Development Board
- HC-SR04 Ultrasonic Sensor
- IR Sensors
- MPU6050 6-Axis Motion Sensor
- 2 × L298N Motor Drivers
- 4 × DC Gear Motors
- OLED Display
- Buzzer
- Red LED
- Lithium Battery
- Four-Wheel Chassis
- Switch
- Breadboard
- Connecting Wires

## 💻 Software Used

- Arduino IDE
- Embedded C/C++
- Bluetooth Controller App
- Serial Monitor

## ⚙️ Working

1. The mobile phone sends a movement command through Bluetooth.
2. ESP32 receives and processes the command.
3. The vehicle can move:
   - `F` → Forward
   - `B` → Backward
   - `L` → Left
   - `R` → Right
   - `S` → Stop
4. The HC-SR04 ultrasonic sensor measures the distance to obstacles.
5. IR sensors provide additional obstacle detection.
6. The MPU6050 monitors vehicle motion and orientation.
7. Sensor information is combined using sensor fusion.
8. The system checks for abnormal or unavailable sensor information.
9. The safety supervisor evaluates the collision risk.
10. If a dangerous obstacle condition is detected, the safety mechanism overrides the normal movement command and stops the vehicle.
11. The OLED, buzzer, and red LED provide system and safety indications.

## ✨ Features

- ESP32-based real-time embedded system
- Bluetooth-controlled four-wheel vehicle
- Ultrasonic obstacle detection
- IR-based obstacle detection
- MPU6050 motion monitoring
- Sensor fusion
- Fault isolation
- Collision-risk evaluation
- Safety supervision
- Emergency vehicle stopping
- OLED status display
- Buzzer and LED safety indication
- Real-time motor control

## 🔌 ESP32 Pin Connections

### L298N Motor Driver 1

|Signal| ESP32 GPIO | Purpose         |
|------|------------|-----------------|
| ENA | GPIO 33     | Speed control   |
| IN1 | GPIO 26     | Motor direction |
| IN2 | GPIO 27     | Motor direction |
| ENB | GPIO 32     | Speed control   |
| IN3 | GPIO 14     | Motor direction |
| IN4 | GPIO 25     | Motor direction |

### L298N Motor Driver 2

|Signal| ESP32 GPIO | Purpose |
|------|------------|-----------------|
| ENA  | GPIO 23    | Speed control   |
| IN1  | GPIO 4     | Motor direction |
| IN2  | GPIO 16    | Motor direction |
| ENB  | GPIO 13    | Speed control   |
| IN3  | GPIO 17    | Motor direction |
| IN4  | GPIO 19    | Motor direction |

### Sensors

| Component | ESP32 GPIO | Purpose |
|---|---:|---|
| HC-SR04 TRIG | GPIO 5 | Trigger signal |
| HC-SR04 ECHO | GPIO 18 | Echo signal |
| Left IR | GPIO 34 | Left obstacle detection |
| Right IR | GPIO 35 | Right obstacle detection |
| MPU6050 SDA | GPIO 21 | I2C data |
| MPU6050 SCL | GPIO 22 | I2C clock |

## 🧪 Testing & Output

### Test Case 1 – Forward Movement

- Bluetooth Command: `F`
- Obstacle: Not Detected
- Vehicle Status: Forward
- Motor: Running

### Test Case 2 – Obstacle Detection

- Obstacle: Detected
- Warning: ON
- Motor: Stopped

### Test Case 3 – Backward Movement

- Bluetooth Command: `B`
- Vehicle Status: Backward
- Motor: Running

### Test Case 4 – Turning

- `L` → Left Turn
- `R` → Right Turn

### Test Case 5 – Stop

- Bluetooth Command: `S`
- Vehicle Status: Stop
- Motor: Stopped

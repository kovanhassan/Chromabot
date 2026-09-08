# 🤖 Chromabot: Autonomous Colour-Sorting Robot

Chromabot is an autonomous colour-sorting robot developed using **VEX IQ hardware and C++**. The robot detects the hue of coloured pencils, determines the appropriate sorting compartment, autonomously moves into position using motor encoder feedback, and dispenses each pencil individually.

The project integrates **embedded C++, multi-sensor feedback, encoder-based motion control, mechanical design, and autonomous decision logic** into a complete mechatronics system.

## 🚀 Features

- **Autonomous hue classification** using real-time optical sensor feedback
- **Distance-based object estimation** with calibration and sensor-error compensation
- **Encoder-feedback positioning** for autonomous compartment alignment
- **Sequential dispensing mechanism** designed to isolate and release one pencil at a time
- **Multi-sensor safety logic** using TouchLED and bumper inputs
- **Ambient-light mitigation** to improve optical sensor reliability
- **Performance tracking** for calibration time, total sorting time, and average sorting time per pencil

Chromabot autonomously sorts pencils into five colour groups: **red, orange/yellow, green, blue, and purple/pink**.

## 🛠 Technologies

- **C++**
- **VEXcode**
- **VEX IQ Robotics**
- Optical sensor
- Distance sensor
- TouchLED sensor
- Bumper sensor
- Motor encoders
- Differential drive system
- Gear-driven dispensing mechanism

## 💻 Software

Chromabot uses a modular **C++ control architecture** that separates calibration, sensing, classification, positioning, dispensing, and performance monitoring.

- `calibrateSize()` – Calibrates pencil dimensions using distance measurements
- `countTools()` – Estimates the number of pencils using calibrated distance data
- `colorDetect()` – Processes optical sensor readings and classifies pencil hue
- `alignBox()` – Uses motor encoder feedback to autonomously position the robot at the correct compartment
- `dump()` – Moves the robot to a safe dumping position, ejects remaining pencils, and terminates operation
- `timeDisplay()` – Calculates and displays calibration and sorting performance

### Autonomous Control Sequence

`Calibrate → Count → Detect → Classify → Align → Dispense → Repeat → Shutdown`

Once initialized, the system repeatedly senses, classifies, positions, and dispenses pencils without requiring manual control.

## ⚙️ Engineering Design

The final robot uses a **four-beam chassis, inclined pencil tray, shielded optical sensing area, differential drive system, and dual-pronged dispensing mechanism**.

The system went through several mechanical and software iterations to improve reliability:

- Added an **optical sensor shield** to reduce interference from ambient lighting
- Reinforced the chassis to improve structural stability
- Implemented a **stopper mechanism** to prevent multiple pencils from entering the dispensing area simultaneously
- Added software compensation for uncertainty in distance-sensor measurements
- Improved tray geometry and surface characteristics to reduce pencil movement issues
- Optimized gear and motor placement to improve dispensing consistency
- Improved wheel configuration to achieve more consistent straight-line movement

These iterations were driven by observed failure modes during testing and used to improve overall system reliability.

## 🧠 Sensor & Control System

Chromabot combines multiple sensor inputs to support autonomous operation.

**Optical Sensor**  
Measures pencil hue and assigns the detected pencil to one of five colour categories.

**Distance Sensor**  
Measures the occupied length of the pencil tray. Combined with calibrated pencil dimensions, the measurement is used to estimate the number of pencils loaded.

**Motor Encoders**  
Provide positional feedback used to determine the robot's location relative to predefined sorting compartments.

**TouchLED**  
Provides user interaction during calibration and operation and allows the remaining pencils to be dumped when required.

**Bumper Sensor**  
Acts as an emergency stop, immediately stopping the motors and terminating operation when triggered.

## 🛡️ Reliability & Safety

Several measures were incorporated to improve reliability under real-world sensor and mechanical limitations:

- **Sensor-error compensation** for variation in distance measurements
- Additional sorting cycles to reduce the probability of pencils remaining unsorted
- Physical shielding to reduce ambient-light interference with hue measurements
- Mechanical isolation to prevent multiple pencils from dispensing simultaneously
- Bumper-based emergency shutdown
- Controlled dump sequence for safely terminating operation

## 📈 Testing & Performance

Chromabot was tested at both the subsystem and fully integrated system levels.

Testing included:

- Pencil-width calibration
- Pencil-count estimation
- Optical hue classification
- Encoder-feedback positioning
- Single-pencil dispensing
- Ambient-light interference testing
- Emergency shutdown
- Dump functionality
- Full autonomous sorting runs with varying pencil quantities and colour sequences

Testing demonstrated reliable colour classification, consistent compartment alignment, successful one-at-a-time dispensing, and complete autonomous sorting cycles despite limitations in the VEX optical and distance sensors.

## 🔧 Engineering Challenges

### Ambient-Light Interference

The optical sensor was sensitive to surrounding white light, which could distort hue measurements. A physical barrier was designed around the sensing area to reduce external light exposure and improve classification consistency.

### Distance Sensor Uncertainty

Small variations in distance measurements could affect the estimated pencil count. Calibration and software compensation were used to reduce the impact of sensor uncertainty.

### Reliable Single-Pencil Dispensing

The dispensing mechanism needed to prevent multiple pencils from entering the release area simultaneously. A stopper bar and dual-pronged gear mechanism were implemented to isolate and release pencils individually.

### Mechanical Stability

Early chassis and tray configurations introduced instability and inconsistent pencil movement. The structure, tray surface, wheel configuration, and component placement were iteratively modified to improve reliability.

## 🔮 Future Improvements

Potential improvements to the system include:

- Higher-resolution optical/RGB sensing with improved ambient-light filtering
- Higher-precision distance sensing
- Fully enclosed optical sensor housing
- Adaptive hue-classification thresholds
- Improved safety and fault-handling logic
- Acceleration and deceleration profiles for smoother motion
- More precise mechanical dispensing and tray geometry

## 📄 Documentation & Demo

- [**Technical Report**](https://drive.google.com/file/d/1iCFc4runeRYamfVcYVUsDAtfJHgA4gGt/view?usp=sharing) – Full engineering report covering the mechanical design, software implementation, testing, verification, and design iterations.

- [**Video Demonstration**](https://drive.google.com/file/d/1-qip-K-SXU5OeHSNBFOychT8EbmqP7bX/view?usp=sharing) – Demonstration of Chromabot performing the autonomous colour-sorting process.

## 📚 Project

Developed for **MTE 100 / MTE 121 — Mechatronics Engineering** at the **University of Waterloo**.

**Group 9 — Fall 2025**

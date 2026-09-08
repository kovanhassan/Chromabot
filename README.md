# 🤖 Chromabot: Autonomous Colour-Sorting Robot

Chromabot is an autonomous colour-sorting robot developed using **VEX IQ hardware and C++**. The robot detects the hue of coloured pencils, determines the appropriate sorting compartment, moves into position using motor encoder feedback, and releases each pencil individually.

The project combines **embedded programming, sensor integration, mechanical design, and autonomous control** into a complete mechatronics system. :contentReference[oaicite:0]{index=0}

## 🚀 Features

- **Hue-based colour detection** using an optical sensor
- **Automatic pencil-count estimation** using distance-sensor calibration
- **Encoder-based positioning** for alignment with colour compartments
- **One-at-a-time dispensing mechanism** using motor-driven pronged gears
- **TouchLED controls** for calibration, operation, and emergency dumping
- **Bumper emergency stop** for collision detection and safe shutdown
- **Performance tracking** for calibration time, sorting time, and average sorting time per pencil

Chromabot sorts pencils into five colour groups: **red, orange/yellow, green, blue, and purple/pink**. :contentReference[oaicite:1]{index=1}

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

The robot's software is divided into modular functions responsible for calibration, sensing, movement, dispensing, and system control.

- `calibrateSize()` – Estimates the width of a pencil
- `countTools()` – Estimates the number of pencils loaded in the tray
- `colorDetect()` – Classifies pencils based on measured hue
- `alignBox()` – Moves the robot to the correct sorting compartment
- `dump()` – Safely ejects remaining pencils and terminates operation
- `timeDisplay()` – Displays calibration and sorting performance

The complete sorting process follows:

`Calibrate → Count → Detect → Align → Release → Repeat → Shutdown`

:contentReference[oaicite:2]{index=2}

## ⚙️ Engineering Design

The final robot uses a **four-beam chassis**, inclined pencil tray, optical sensing area, differential drive system, and dual-pronged dispensing mechanism.

Several design iterations were required to improve reliability, including:

- Adding an optical sensor shield to reduce ambient-light interference
- Reinforcing the chassis to improve stability
- Adding a stopper mechanism to prevent multiple pencils from entering simultaneously
- Compensating for distance-sensor inaccuracies through software
- Optimizing the tray and gear placement to reduce jams

:contentReference[oaicite:3]{index=3}

## 📈 Testing & Performance

Chromabot was tested across its major subsystems, including:

- Pencil-width calibration
- Pencil-count estimation
- Hue classification
- Encoder-based alignment
- Single-pencil dispensing
- Emergency shutdown
- Full autonomous sorting runs

Testing demonstrated reliable colour classification, consistent movement, and successful autonomous operation despite limitations in the VEX optical and distance sensors. :contentReference[oaicite:4]{index=4}

## 👨‍💻 My Contributions

My primary contributions included both **software development and sensor integration**.

- Developed `countTools()` for estimating the number of pencils using calibrated distance measurements
- Developed `alignBox()` for encoder-based movement between sorting compartments
- Mounted and positioned the distance sensor
- Designed and installed a shield above the optical sensor to reduce ambient-light interference
- Contributed to system integration, testing, and debugging

:contentReference[oaicite:5]{index=5}

## 📚 Project

Developed for **MTE 100 / MTE 121 — Mechatronics Engineering** at the **University of Waterloo**.

**Group 9 — Fall 2025**

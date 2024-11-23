# Pixhawk Servo Connection Guide

This repository provides an **easy-to-follow guide** for connecting and configuring servos with a Pixhawk flight controller. Whether you're a beginner or an advanced user, this guide simplifies the process of controlling servos with RC transmitter channels and setting up relay functionality.

---

## Key Features

**Channel Mapping  🎮:**  
- **Channel 6 (CH-6)** on the transmitter is mapped to **Servo 14 (AUX 6)** on Pixhawk.
- **Channel 9 (CH-9)** on the transmitter is mapped to **Servo 13 (AUX 5)** on Pixhawk.
- **Relay Functionality:** Configure **on/off switches** for servo control in Flight modes.

---

## What You Need

| **Hardware**                    | **Quantity** |
|----------------------------------|--------------|
| 🖥️ **Pixhawk Flight Controller** | 1            |
| ⚙️ **SG90 Servos (or equivalent)** | 2            |
| 🎛️ **RC Transmitter** (e.g., Taranis, 9+ channels) | 1 |
| 📡 **Receiver** (supports PWM/PPM/S.Bus) | 1 |
| 🔌 **Connection Cables**         | As needed    |

---

## Wiring Diagram

Connect your components based on the wiring diagram below:

![Wiring Diagram](how_to_connect_servo_to_pixhwack.jpg)

---

## Step-by-Step Setup 🔧

###  1. Wiring the Components

- Connect the servo signal wires to the appropriate AUX pins on Pixhawk:
  - **Servo 14** connects to **AUX 6**.
  - **Servo 13** connects to **AUX 5**.
- Connect your RC transmitter to the receiver. Ensure the receiver is properly linked to the Pixhawk flight controller using PWM, PPM, or S.Bus output.

---

### 2. Configuring Servo Functions

In **QGroundControl** or **Mission Planner**:

1. **Open the Parameters list:**
   - Assign **Servo 13 Function** to `RCIN9` (linked to **Channel 9** on the transmitter).
   - Assign **Servo 14** to `RCIN6` (linked to **Channel 6** on the transmitter).

2. **Set PWM Values**:
   - **Minimum:** 800 PWM
   - **Maximum:** 2200 PWM
   - **Trim:** 1500 PWM (neutral position)

---

### 3. Flight Mode Setup

1. Go to the **Flight Modes Setup** section in your software.
2. Map transmitter switches to relay control:
   - **CH-9 → Configure to "Relay On/Off" for controlling Servo 13**.
   - **CH-6 → Configure to "Relay On/Off" for controlling Servo 14**.
3. Verify PWM thresholds for activating relay functions.

---

### 4. Testing Your Setup

1. Power on your Pixhawk and connect it to your configuration software.
2. Toggle the **CH-6** and **CH-9** switches on your transmitter:
   - **CH-6 controls Servo 14 (AUX 6)**.
   - **CH-9 controls Servo 13 (AUX 5)**.
3. Observe servo movement and relay activation.
4. Adjust PWM values if necessary for smooth operation.

---

## License 📜

This project is licensed under the **MIT License**. Feel free to use, modify, and share it as needed.

---

## Pro Tips 💡

- **Check Compatibility:** Ensure your servos are compatible with the Pixhawk (voltage and current ratings).
- **Secure Wiring:** Use zip ties or clips to keep your wiring neat and avoid accidental disconnections.
- **Calibrate Servos:** Use the transmitter and software to fine-tune servo positions for precise control.

---

## Connect with the Community 🔗 

-  [Pixhawk- DroneCAN](https://docs.px4.io).
- [Pixhawk- Lidar](https://discuss.px4.io).

---


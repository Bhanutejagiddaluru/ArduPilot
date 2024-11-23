# Pixhawk Servo Connection

This repository provides a simple and clear guide to connect and configure servos with the Pixhawk flight controller. The goal is to demonstrate how to control servos using RC transmitter channels and configure relay functionality for on/off control.

---

## Key Features

- **Channel 6 (CH-6)** on the transmitter is mapped to **Servo 14 (AUX 6)** on Pixhawk.
- **Channel 9 (CH-9)** on the transmitter is mapped to **Servo 13 (AUX 5)** on Pixhawk.
- **Flight modes** are configured to switch relays on or off for connected servos.

---

## Hardware Requirements

To follow this guide, you will need the following:

1. **Pixhawk Flight Controller**
2. **Servos (e.g., SG90)** – 2 pieces
3. **Transmitter** – e.g., Taranis or similar, with at least 9 channels
4. **Receiver** – Supporting PWM/PPM/S.Bus outputs
5. **Connection cables**

---

## Wiring Diagram

Refer to the image below for detailed wiring instructions:

![Wiring Diagram](how_to_connect_servo_to_pixhwack.jpg)

---

## Step-by-Step Instructions

### 1. Wiring the Components

- Connect the servo signal wires to the appropriate AUX pins on Pixhawk:
  - **Servo 14** connects to **AUX 6**.
  - **Servo 13** connects to **AUX 5**.
- Connect your RC transmitter to the receiver. Ensure the receiver is properly linked to the Pixhawk flight controller using PWM, PPM, or S.Bus output.

---

### 2. Assign Servo Functions in QGroundControl or Mission Planner

1. Open your flight controller configuration software (e.g., QGroundControl or Mission Planner).
2. Assign functions to the servo outputs:
   - **Servo 13 Function**: Set to `RCIN9` (linked to Channel 9 on your transmitter).
   - **Servo 14 Function**: Set to `RCIN6` (linked to Channel 6 on your transmitter).
3. Configure PWM values:
   - Minimum: 800 PWM
   - Maximum: 2200 PWM
   - Trim: 1500 PWM (neutral position)

---

### 3. Set Up Flight Modes

1. Navigate to the **Flight Modes Setup** section in the software.
2. Map the transmitter channels to relay control functions:
   - **Channel 8**: Configure to "Relay On/Off" for controlling Servo 13.
   - **Channel 6**: Configure to "Relay On/Off" for controlling Servo 14.
3. Ensure the correct PWM values for channel switches:
   - Set thresholds to trigger relays when switches are toggled.

---

### 4. Test the Configuration

1. Power on the Pixhawk and connect it to QGroundControl or Mission Planner.
2. Use the transmitter switches (CH-6 and CH-9) to test the movement and relay control of Servo 14 and Servo 13.
3. Verify that the servos respond correctly:
   - Toggle switches to move servos or activate relays.
   - Adjust PWM values if necessary for smoother operation.

---

## Example Configuration Files

If you'd like to skip manual setup, you can use the preconfigured parameter files included in this repository:
- **`QGroundControl_settings.txt`** – Example configuration for QGroundControl.
- **`MissionPlanner_params.param`** – Example parameters for Mission Planner.

Simply upload the files to your flight controller to replicate the settings.

---

## License

This project is licensed under the [MIT License](LICENSE). You are free to use, modify, and share this guide.

---

## Additional Notes

- Ensure your servos are compatible with the Pixhawk controller (check voltage and current ratings).
- Double-check wiring to avoid damage to components.
- For troubleshooting tips, refer to the official Pixhawk documentation or community forums.

---

Let me know if you encounter any issues or have questions about the setup!

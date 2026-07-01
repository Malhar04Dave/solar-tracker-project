# Solar Tracker Project

This project uses an Arduino to dynamically position a solar panel to maximize energy absorption. By utilizing four Light Dependent Resistors (LDRs) placed in a cross configuration, the system detects the direction of the highest light intensity and adjusts two servo motors (horizontal and vertical) to align the panel accordingly.

---

## 🛠 Hardware Requirements

* **Microcontroller:** Arduino Uno (or compatible board)
* **Sensors:** 4x Light Dependent Resistors (LDRs)
* **Actuators:** 2x Servo Motors (SG90 or MG995, depending on panel size)
* **Resistors:** 4x 10kΩ resistors (for voltage dividers)
* **Power:** External 5V/6V power supply for servos (do not power servos directly from the Arduino 5V pin)
* **Structure:** Solar panel mounting bracket, breadboard, and jumper wires

---

## ⚙️ How It Works



1.  **Sensing:** The four LDRs act as the "eyes" of the system. By arranging them in a cross and using them as part of a voltage divider circuit, the Arduino reads varying analog voltages based on the intensity of light hitting each resistor.
2.  **Comparison:** The code calculates the differences between the averages of the top vs. bottom sensors and the left vs. right sensors. This allows the system to determine which direction the light source is moving.
3.  **Correction:** If the difference between these averages exceeds a defined threshold, the Arduino commands the servo motors to rotate. This continuous adjustment ensures the solar panel remains perpendicular to the incoming light rays for maximum efficiency.
4.  **Stability:** The inclusion of a small threshold (deadband) and a short delay ensures that the motors do not jitter or constantly hunt for position due to minor, fleeting changes in ambient light or shadows.

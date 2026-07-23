# Smart Gate Entry System Simulation

## 🔗 Simulation Link
**[https://wokwi.com/projects/470304920857053185]**

## 📌 Project Overview
This project is an Arduino-based simulation of a smart electronic entry gate. Designed and simulated using the **Wokwi** online platform, the system automates vehicle entry by detecting cars, simulating a license plate security scan, issuing a ticket, and controlling a barrier gate.

## 🚀 System Workflow (Scenario)
The system operates automatically in the following sequence when a vehicle approaches:
1. **Vehicle Detection:** An ultrasonic sensor continuously monitors the entrance. When a car comes within **50 cm**, the system activates.
2. **Camera Scan (Stepper Motor):** A security camera (represented by a stepper motor) rotates **45° to the right**, sweeps **90° to the left**, and then returns to the **center** to simulate scanning the vehicle's license plate.
3. **Ticket Issuance (LED):** An LED indicator turns on for **2 seconds** to simulate the process of printing and dispensing an entry ticket.
4. **Gate Operation (Servo Motor):** The gate barrier (represented by a servo motor) raises **90°** to allow the vehicle to pass. It remains open for **5 seconds** before automatically closing (returning to 0°).

---

## 🛠️ Hardware Components
*   **1x Arduino Uno** (The main microcontroller)
*   **1x Bipolar Stepper Motor** (Simulates the scanning camera)
*   **1x Servo Motor** (Simulates the gate barrier)
*   **1x Ultrasonic Sensor - HC-SR04** (Vehicle distance detection)
*   **1x LED** (Ticket issuance indicator)
*   **1x 220Ω Resistor** (For the LED)
*   **1x Breadboard & Jumper Wires**

---

## 🔌 Pin Configuration (Wiring Guide)

| Component | Component Pin | Arduino Uno Pin | Notes |
| :--- | :--- | :--- | :--- |
| **Stepper Motor** | A+ (IN1) | `D8` | Directly connected (Bipolar) |
| | A- (IN2) | `D9` | Directly connected |
| | B+ (IN3) | `D10` | Directly connected |
| | B- (IN4) | `D11` | Directly connected |
| **Servo Motor** | Signal / PWM | `D4` | |
| | VCC / Power | `5V` | Via Breadboard |
| | GND | `GND` | Via Breadboard |
| **Ultrasonic Sensor**| TRIG | `D5` | |
| | ECHO | `D6` | |
| | VCC | `5V` | Via Breadboard |
| | GND | `GND` | Via Breadboard |
| **LED** | Anode (+) | `D3` | Connect via a 220Ω Resistor |
| | Cathode (-) | `GND` | Via Breadboard |

---

## 💻 Software Dependencies
This code relies on standard Arduino libraries that are built-in:
*   `<Stepper.h>` - To control the bipolar stepper motor.
*   `<Servo.h>` - To control the gate barrier servo.

---

## ⚙️ How to Run the Simulation (Wokwi)
1. Open the [Wokwi Simulator](https://wokwi.com/) and create a new **Arduino Uno** project.
2. Add the hardware components listed above from the **(+)** menu.
3. Wire the components exactly as described in the **Pin Configuration** table.
4. Copy the provided `C++` code and paste it into the `sketch.ino` editor.
5. Click the **Play (▶)** button to start the simulation.
6. **Trigger the System:** Click on the Ultrasonic Sensor. A slider will appear. Drag the distance slider to **below 50 cm** to simulate a car pulling up to the gate. Watch the automated sequence unfold!

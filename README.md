# Smart-door-lock-system
# Arduino Smart Lock using RFID, Fingerprint Sensor, and Servo Motor

This project demonstrates a smart lock system built using an Arduino UNO, an RFID module (MFRC522), a fingerprint sensor (R307), and a servo motor. It allows users to unlock a digital lock using either RFID cards or fingerprints, depending on the selected mode via a push button.

## 📷 Project Overview

![Wiring Diagram](A_detailed_digital_illustration_diagram_displays_a.png)

## 🔧 Components Used

- Arduino UNO
- MFRC522 RFID Reader
- R307 Fingerprint Sensor (4-pin version)
- SG90 Servo Motor (for lock mechanism)
- Push Button (for switching modes)
- External 5V power supply (for servo motor)
- Jumper wires and breadboard

## ⚙️ Features

- **Dual Authentication**: Unlock via RFID or fingerprint.
- **Servo Locking Mechanism**: Locks at 0°, unlocks at 180°.
- **Push Button Mode Selector**: Allows user to select between fingerprint or RFID authentication.
- **Serial Monitor Logging**: Displays real-time actions and feedback.

## 🔌 Wiring Summary

### MFRC522 RFID Connections:
| RFID Pin | Arduino Pin |
|----------|--------------|
| SDA      | D10          |
| SCK      | D13          |
| MOSI     | D11          |
| MISO     | D12          |
| IRQ      | Not used     |
| GND      | GND          |
| RST      | D9           |
| 3.3V     | 3.3V         |

### R307 Fingerprint Sensor (4-pin):
| Fingerprint Pin | Arduino Pin |
|------------------|--------------|
| VCC              | 5V           |
| GND              | GND          |
| TX               | D2 (SoftwareSerial RX) |
| RX               | D3 (SoftwareSerial TX) |

### Servo Motor:
- Signal → D5
- VCC → External 5V
- GND → Common GND

### Push Button:
- One end to D4
- Other end to GND (with `INPUT_PULLUP` mode)

## 🧠 How it Works

1. Press the push button to enter **Fingerprint Mode**.
2. Otherwise, it remains in **RFID Mode** by default.
3. If a recognized RFID tag or fingerprint is detected, the servo rotates to 180° to unlock the lock.
4. After 5 seconds, the servo returns to 0° to relock.
5. All events are logged to the Serial Monitor.

## 🧪 Testing

- Upload the code using Arduino IDE.
- Use the Serial Monitor at 9600 baud to observe logs.
- Register at least one fingerprint and note your RFID card UID.
- Edit `authorizedUID` in code to match your card.


Created with ❤️ using Arduino.

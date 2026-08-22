# 🛡️ Smart Self-Defense Shoe

> **An IoT-based wearable safety prototype built using NodeMCU ESP8266 and embedded hardware to provide a discreet emergency trigger and rapid defensive response.**

The **Smart Self-Defense Shoe** is an embedded-systems project that integrates electronics into footwear to provide a compact emergency-response mechanism.

The prototype uses a **NodeMCU ESP8266**, a **panic button**, an **I²C 16×2 LCD**, and a **relay-controlled output circuit**. When the user activates the hidden panic button, the controller changes the system state, displays an alert on the LCD, and activates the relay for a predefined period.

The project demonstrates the integration of **microcontrollers, digital input handling, display communication, relay control, embedded programming, and hardware integration** into a wearable prototype.

---

## ✨ Features

* 🚨 Discreet panic-button activation
* 🧠 NodeMCU ESP8266-based control system
* 📟 16×2 I²C LCD status display
* 🔌 Relay-controlled output
* ⏱️ Automatic timed activation
* 🔋 Portable battery-powered design
* 👟 Electronics integrated into footwear
* 🔧 Embedded hardware and software integration
* 🛠️ Arduino IDE / C++ firmware
* 📐 Custom circuit and hardware design

---

## 🎯 Project Objectives

The project was developed to explore how embedded systems and IoT technologies can be integrated into wearable safety devices.

### Main objectives

1. Develop a compact wearable emergency-response prototype.
2. Detect an emergency through a discreet physical trigger.
3. Process the trigger using a microcontroller.
4. Provide immediate visual feedback to the user.
5. Control an external circuit through a relay.
6. Automatically deactivate the output after a predefined period.
7. Demonstrate practical integration of embedded electronics into footwear.

---

## 🧠 System Overview

```text
                  ┌─────────────────────┐
                  │   Panic Button      │
                  │       D5            │
                  └──────────┬──────────┘
                             │
                             ▼
                  ┌─────────────────────┐
                  │  NodeMCU ESP8266    │
                  │                     │
                  │  Control + Logic    │
                  └───────┬───────┬─────┘
                          │       │
                  I²C     │       │ D0
                          │       │
                          ▼       ▼
                ┌────────────┐  ┌────────────┐
                │ 16×2 LCD   │  │   Relay    │
                │   I²C      │  │   Module   │
                └────────────┘  └─────┬──────┘
                                      │
                                      ▼
                              External Output
                                  Circuit
```

---

## 🔄 How It Works

### 1. System Startup

The NodeMCU initializes the LCD, relay and panic-button input.

The LCD displays:

```text
System Ready
Safe
```

### 2. Emergency Trigger

The panic button is connected to **D5** using `INPUT_PULLUP`.

When the button is pressed, the controller detects the LOW signal.

### 3. Alert State

The LCD changes to:

```text
!!! ALERT !!!
IN DANGER
```

### 4. Relay Activation

The NodeMCU activates the relay through **D0**.

The relay controls the connected external circuit.

### 5. Automatic Deactivation

The firmware keeps the relay active for the programmed period and then switches it off automatically.

The LCD returns to:

```text
System Ready
Safe
```

This prevents the relay from remaining continuously active.

---

# 🔌 Hardware Components

| Component                                 | Purpose                                                 |
| ----------------------------------------- | ------------------------------------------------------- |
| **NodeMCU ESP8266**                       | Main microcontroller and control logic                  |
| **16×2 I²C LCD**                          | Displays system status                                  |
| **Relay Module**                          | Electrically controls the external output circuit       |
| **Panic Button**                          | Emergency trigger input                                 |
| **High-Voltage Generator / Boost Module** | External defensive output circuit used in the prototype |
| **Rechargeable Battery**                  | Portable power source                                   |
| **Metal Plate / Conductive Element**      | Part of the prototype output mechanism                  |
| **Wires / PCB**                           | Electrical connections and assembly                     |
| **Shoe**                                  | Wearable project platform                               |

---

# 📌 NodeMCU Pin Configuration

| Component       | NodeMCU Pin     |
| --------------- | --------------- |
| Relay           | **D0 / GPIO16** |
| Panic Button    | **D5**          |
| LCD SDA         | **D2**          |
| LCD SCL         | **D1**          |
| LCD I²C Address | **0x27**        |

> **Note:** The LCD address may vary between modules. `0x27` is the address used by the current source code.

---

# 💻 Software

### Development Environment

* **Arduino IDE**
* **C/C++**
* **ESP8266 Arduino Core**

### Libraries

```cpp
#include <Wire.h>
#include <LiquidCrystal_PCF8574.h>
```

### Main Software Responsibilities

The firmware:

* Reads the panic-button state.
* Controls the relay.
* Updates the LCD.
* Maintains the emergency/normal system states.
* Implements timed relay activation.
* Automatically returns the system to its normal state.

---

# 📂 Repository Structure

```text
smart-self-defense-shoe/
│
├── Code.txt
├── README.md
│
├── Circuit Diagram.jpeg
│
├── Photo 1.jpeg
├── Photo 2.jpeg
│
├── Video1.mp4
├── Video 2.mp4
│
├── EMBEDDED_PROJECT.pdf
└── IES_documentationn[1][1].pdf
```

---

# 📐 Circuit Diagram

The project circuit diagram shows the connection between the NodeMCU, LCD, relay, panic button and supporting hardware.

![Circuit Diagram](Circuit%20Diagram.jpeg)

---

# 📸 Project Photos

### Project Prototype

![Project Photo 1](Photo%201.jpeg)

### Hardware / Prototype

![Project Photo 2](Photo%202.jpeg)

---

# 🎥 Project Demonstration

The repository contains demonstration videos of the working prototype:

* [▶️ Watch Demo Video 1](Video1.mp4)
* [▶️ Watch Demo Video 2](Video%202.mp4)

> Depending on GitHub's browser support for large video files, you may need to download the video to view it.

---

# 📜 Source Code

The current NodeMCU firmware is available here:

**[View Code.txt](Code.txt)**

The firmware controls the panic button, LCD display and relay according to the prototype's operating logic.

---

# 📚 Documentation

The repository contains the project's academic documentation and reports:

* **[Embedded Systems Project Report](EMBEDDED_PROJECT.pdf)**
* **[Project Documentation](IES_documentationn%5B1%5D%5B1%5D.pdf)**

These documents contain the project's objectives, components, system functionality, circuit documentation and project details.

---

# 👥 Team & Contributions

## Kathan Patel

**GitHub:** [Kathan-x](https://github.com/Kathan-x)

### Contributions

* Developed and maintained the **NodeMCU ESP8266 firmware**.
* Implemented panic-button input handling.
* Implemented relay control logic.
* Integrated the **16×2 I²C LCD**.
* Worked on the NodeMCU pin configuration and hardware integration.
* Tested the embedded control system.
* Maintained the GitHub repository and project version history.
* Organized project source code, documentation and demonstration files.

---

## Heer Patel

**GitHub:** [Heerrr166](https://github.com/Heerrr166)

### Contributions

* Collaborator on the Smart Self-Defense Shoe project.
* Contributed to project development and documentation.
* Participates in project testing, review and further development.
* Maintains her work through her GitHub contribution branch/fork.

> Contribution details can be expanded as additional work is committed to the repository.

---

## Aryan Bochiya

**GitHub:** —
**Role:** Project team member

Aryan is a member of the original academic project team. Additional contribution details can be added as the team's individual responsibilities are documented.

---

# 🌱 Future Improvements

The current prototype can be extended with additional safety and IoT capabilities.

Possible future improvements include:

* 📱 Mobile application integration
* 🌐 IoT-based emergency notifications
* 📍 GPS-based location sharing
* 📡 GSM-based emergency communication
* 🔔 Buzzer/vibration feedback
* 🔋 Battery-level monitoring
* 🖥️ Improved OLED interface
* 🔐 Additional trigger/safety mechanisms
* 📊 Event logging and monitoring
* ⚡ Improved power-management system
* 🧪 More extensive hardware and reliability testing

---

# ⚠️ Safety Notice

This repository documents an **academic embedded-systems prototype**.

The project includes components capable of generating high voltage. High-voltage circuits can cause serious injury, burns, electrical shock, fire or equipment damage.

**Do not experiment with high-voltage circuitry without appropriate electrical knowledge, supervision and safety precautions.**

The defensive-output portion should be treated as a laboratory prototype rather than a consumer-ready safety product. The design should undergo proper electrical, mechanical and safety validation before any real-world deployment.

---

# 🎓 Academic Project

**Course:** Introduction to Embedded Systems
**Program:** BCA / iMCA
**Project:** Smart Self-Defense Shoe
**Technology:** Embedded Systems / IoT
**Controller:** NodeMCU ESP8266

---

# ⭐ Project Status

**Status:** Prototype / Academic Project

The current repository contains:

* ✅ NodeMCU firmware
* ✅ Hardware documentation
* ✅ Circuit diagram
* ✅ Project photographs
* ✅ Demonstration videos
* ✅ Academic project reports
* ✅ Git-based version control
* ✅ Collaborative development setup

---

## ⭐ Support the Project

If you find this project interesting:

⭐ **Star the repository**
🍴 **Fork the repository**
🐛 **Open an issue** for bugs or suggestions
🔀 **Submit a pull request** with improvements

---

## 📄 License

This project was developed as an academic project.

If you plan to reuse, modify or distribute the hardware design or software, please contact the project authors first.

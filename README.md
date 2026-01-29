# Smart-Security-Door-System-STM32F4-
This project is a microcontroller-based security system developed in C language using Keil uVision for the STM32F4 (Otak Kecil board). The system is designed to provide real-time monitoring and automated alerts for home security.
# 🛡️ Smart Security Door System (STM32F4)
> **Advanced Home Security using STM32F446 (Otak Kecil), MQ-2, and FC-51 Sensors.**

---

## 🚀 Overview
A high-performance security solution developed in **C Language** that integrates real-time environmental sensing and human detection. This system prioritizes fire safety and visitor alerts using **External Interrupts (EXTI)** for instantaneous response.

![Project Header](https://via.placeholder.com/1000x400?text=SMART+SECURITY+DOOR+-+STM32F4+PROJECT+HEADER) 
*(Tips: Guna gambar litar atau mockup projek kau kat sini)*

---

## ✨ Key Features

* **🔥 Dual-Level Priority Safety** – Integrated **MQ-2 Smoke Sensor** that overrides all functions during fire emergencies.
* **👤 Intelligent Human Detection** – Uses **FC-51 IR Sensor** to detect visitors and display a "Hi" (H1) greeting.
* **⚡ Zero-Lag Calling Bell** – Implements **EXTI1 (External Interrupt)** on PB1 for a real-time visitor bell that works even if the main code is busy.
* **📟 Visual Feedback System** – Dual 7-Segment display output to show system status (**F1** for Fire, **H1** for Human).
* **🛠️ Bare-Metal Optimization** – Coded using direct **Register Manipulation (GPIO, RCC, EXTI)** for maximum speed and efficiency.

---

## 🛠️ How It Works

1.  **Sensing Stage:** The system constantly monitors PA0 (Smoke) and PA1 (Motion) using digital polling.
2.  **Logic Processing:**
    * **Priority 1 (Fire):** Smoke detected? → Trigger **Continuous Buzzer** + Display **"F1"**.
    * **Priority 2 (Visitor):** Motion detected? → Turn on **LEDs** + Display **"H1"**.
3.  **Interrupt Stage:** When SW4 (PB1) is pressed, the hardware triggers a callback to `EXTI1_IRQHandler`, sounding the buzzer immediately.

---

## 📊 System Logic & Priority Table

| Condition | Priority | 7-Seg Display | Buzzer (PD2) | LEDs (PB12-15) |
| :--- | :---: | :---: | :---: | :---: |
| **Smoke Detected** | 🔴 High | **F1** | 🔊 Continuous | ✅ ON |
| **Motion Detected** | 🟡 Med | **H1** | 🔇 OFF | ✅ ON |
| **Bell Pressed** | ⚡ Instant | - | 🔔 Pulsed | - |
| **Idle** | ⚪ Low | (Blank) | 🔇 OFF | ❌ OFF |

---

## 🏗️ Hardware Architecture
* **MCU:** STM32F446 (Otak Kecil Board)
* **Sensors:** MQ-2 (Smoke), FC-51 (IR Obstacle)
* **Indicators:** Active Buzzer, Dual 7-Segment, 4x LEDs
* **Software:** Keil uVision 5, KiCad 9.0 (PCB Design)

---

## 🚀 Potential Upgrades
* **📱 Mobile Integration:** Connect an **ESP8266** to send "FIRE ALERT" notifications to your phone.
* **🔒 Solenoid Lock:** Add a 12V Solenoid to automatically lock/unlock the door via a Relay.
* **📷 Camera Trigger:** Capture a photo when the motion sensor or bell is triggered.

---

## 👥 Meet The Team
* **Azim Umar** - *System Architecture*
* **Amir Asyraf** - *Firmware Development*
* **Melvin Jude** - *Hardware Integration*
* **Tan Zi Long** - *Documentation & Testing*

---
*Submitted to: Ir. Ts. Dr. Fauzan Khairi bin Che Harun*

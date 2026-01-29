# 🛡️ Smart Security Door System (STM32F4)
> **An Advanced Embedded Security Solution featuring Priority-Sensing, Hardware Interrupts, and Bare-Metal Optimization.**

---

## 🚀 Project Overview
This project implements an intelligent home security system using the **ARM Cortex-M4 (STM32F446)** architecture. Developed entirely in **C** via **Keil uVision**, the system manages environmental safety and visitor access by interfacing multiple sensors with high-efficiency register-level control.

---

## 📂 Project Structure
To make it easier for you to navigate, this repository is divided into 4 main categories:

* **📁 [Firmware_Code](./Firmware_Code)**: Contains all C source files (`main.c`), header files, and Keil uVision project files.
* **📁 [Project_Documentation](./Project_Documentation)**: Full report, objectives, and detailed explanation of the Smart Security Door system.
* **📁 [Flowcharts](./Flowcharts)**: Visual logic representation of the system (Priority sensing and EXTI logic).
* **📁 [Circuit_Diagrams](./Circuit_Diagrams)**: Hardware schematics designed using KiCad 9.0, including pin assignments.

---

## ✨ Key Engineering Features
* **🔥 Critical Priority Logic** – The MQ-2 Smoke Sensor is set as the highest priority; detection triggers an immediate emergency "F1" alert.
* **⚡ Hardware Interrupt (EXTI)** – The calling bell (SW4) is tied to **EXTI1**, ensuring an instantaneous buzzer response without polling lag.
* **👤 Motion-Activated Greeting** – Integrated **FC-51 IR Sensor** logic to detect human presence and display "H1" (Hi) greeting.
* **🛠️ Bare-Metal Optimization** – Direct register access for GPIO and RCC configuration to ensure ultra-fast hardware response.

---

## 📊 System Logic & Priority Table

| Condition | System Priority | Display Code | Buzzer State | LED Status |
| :--- | :---: | :---: | :---: | :---: |
| **Smoke Detected** | 🔴 1 (Critical) | **F1** | Continuous | All Active |
| **Motion Detected** | 🟡 2 (Standard) | **H1** | OFF | All Active |
| **Bell Triggered** | ⚡ Async | - | Pulsed (EXTI) | No Change |

---

## 🚀 Potential Upgrades
* **📱 IoT Connectivity**: Integration with ESP8266 for real-time mobile notifications.
* **🔒 Biometric Access**: Adding fingerprint or keypad modules for secondary authentication.
* **💾 Data Logging**: Utilizing EEPROM to log security event timestamps.

---

## 👥 Development Team
* **Azim Umar** | **Amir Asyraf** | **Melvin Jude** | **Tan Zi Long**

---
*Submitted to: Ir. Ts. Dr. Fauzan Khairi bin Che Harun*
*Bachelor of Electronic Engineering | Universiti Teknologi Malaysia*

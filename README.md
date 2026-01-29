# 🛡️ Smart Security Door System (STM32F4)
> **An Advanced Embedded Security Solution featuring Priority-Sensing and Hardware Interrupts.**

---

## 🚀 Overview
This project implements an intelligent home security system using the **ARM Cortex-M4 (STM32F446)** architecture. Developed entirely in **C** via **Keil uVision**, the system manages environmental safety and visitor access by interfacing multiple sensors with high-efficiency register-level control.



---

## ✨ Key Engineering Features

* **🔥 Critical Priority Logic** – The system treats the **MQ-2 Smoke Sensor** as the highest priority input. Upon detection, it overrides all other processes to activate a continuous emergency alarm and visual "F1" (Fire) alert.
* **⚡ Hardware Interrupt (EXTI) Integration** – The calling bell (SW4) is tied to an **External Interrupt (EXTI1)** on Port B. This ensures an instantaneous buzzer response, providing seamless user interaction without polling lag.
* **👤 Motion-Activated Greeting** – Integrated **FC-51 IR Sensor** logic to detect human presence. The system transitions from Idle to a greeting state, displaying "H1" (Hi) on the Seven-Segment display.
* **🛠️ Bare-Metal Optimization** – All GPIO configurations, clock gating (RCC), and interrupt vectors are handled via **direct register access**, ensuring minimal memory footprint and ultra-fast hardware response.

---

## 🛠️ Hardware Specifications
* **MCU:** STM32F446 (Otak Kecil Development Board)
* **Sensing:** MQ-2 Gas/Smoke Sensor, FC-51 Infrared Obstacle Sensor
* **Visual Output:** Dual 7-Segment Display, 4x System LEDs
* **Audio Output:** Active Piezo Buzzer
* **Design Tools:** KiCad 9.0 (Schematic), Keil uVision 5 (Firmware)

---

## 📊 System Logic & Priority Table

| Condition | System Priority | Display Code | Buzzer State | LED Status |
| :--- | :---: | :---: | :---: | :---: |
| **Smoke Detected** | 🔴 1 (Critical) | **F1** | Continuous | All Active |
| **Motion Detected** | 🟡 2 (Standard) | **H1** | OFF | All Active |
| **Bell Triggered** | ⚡ Async | - | Pulsed (EXTI) | No Change |
| **Idle State** | ⚪ 3 (Passive) | (Blank) | Silent | All Inactive |



---

## 🏗️ Firmware Architecture
The firmware is structured into modular subroutines to enhance maintainability:
* `system_init()`: Configures AHB1 bus clocks and GPIO modes.
* `EXTI1_IRQHandler()`: Handles the asynchronous calling bell trigger.
* `display_F1()` / `display_H1()`: Encapsulated logic for 7-Segment visualization.

---

## 👥 Development Team
* **Azim Umar** | **Amir Asyraf** | **Melvin Jude** | **Tan Zi Long**

---
*Submitted to: Ir. Ts. Dr. Fauzan Khairi bin Che Harun*
*Bachelor of Electronic Engineering | Universiti Teknologi Malaysia*

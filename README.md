# 🛡️ SecurityDoor-STM32: Intelligent Priority-Based Security System

**SecurityDoor-STM32** is a high-performance embedded monitoring system built on the **STM32F446RET (Otak Kecil Board)**. It features real-time smoke detection, human presence sensing, and an interrupt-driven visitor alert system—all managed through optimized bare-metal register logic.



## ✨ Key Features

* **Dual-Sensor Fusion** – Seamlessly integrates an **MQ-2 Smoke Sensor** and **FC-51 IR Sensor** with hardware-level noise filtering.
* **Emergency Fire Override** – Automated system-wide priority that triggers a continuous siren and "F1" (Fire) visual alert upon smoke detection.
* **Smart Greeting Logic** – Intelligent motion tracking that activates 4x LED indicators and displays a "H1" (Hi) greeting on a Seven-Segment display.
* **Zero-Latency Interrupt Bell** – Uses **EXTI1** hardware interrupts to provide an instantaneous calling bell response, bypassing main loop execution.
* **Optimized Visual Feedback** – High-speed display control via **Seven-Segment Multiplexing**, ensuring flicker-free status updates.
* **Bare-Metal Performance** – Utilizes **BSRR** and **IDR** registers for atomic hardware manipulation, achieving ultra-fast execution speeds.

## 🛠️ How It Works

* **Sensing Stage** – The STM32 polls the environment at the microsecond level. The system uses digital signal processing to verify inputs from the MQ-2 and FC-51 sensors to prevent false triggers.
* **Logic Processing** – Features a **Priority-Based Task Scheduler**. If smoke is detected, the system immediately suspends standard monitoring and enters **Emergency Mode**.
* **Actuation Stage** – It updates the **Dual 14-pin Seven-Segment Display** with HEX codes ("F1", "H1") and triggers high-decibel audible alerts via the active buzzer.
* **Interrupt Handling** – Pressing the **SW4 button** triggers an asynchronous hardware interrupt, instantly toggling the buzzer state without stalling the CPU's main monitoring tasks.



## 📊 Logic & Feedback Table

| Input Condition | LED (PB12-15) | 7-Seg Display | Buzzer (PD2) | Logic Priority |
| :--- | :---: | :---: | :---: | :---: |
| **🔥 Smoke Detected** | 🔴 ALL ON | **F1** | 🔊 Continuous | 🏆 1 (Highest) |
| **👤 Motion Detected** | 🔴 ALL ON | **H1** | 🔇 Silent | ⭐ 2 (Standard) |
| **🔔 Bell Pressed** | (No Change) | (No Change) | 🔊 Pulsed | ⚡ EXTI (Async) |
| **⚪ Idle Mode** | 🌑 ALL OFF | (Blank) | 🔇 Silent | 💤 3 (Lowest) |

## 🚀 Potential Upgrades

* **IoT Gateway Integration** – Interfacing an **ESP8266** module to broadcast fire alerts to a cloud-based dashboard via MQTT protocol.
* **Solenoid Actuator Control** – Adding a 12V relay system to automatically engage/disengage electromagnetic door locks.
* **Deep Sleep Optimization** – Implementing **Low Power Modes** (Sleep/Stop) to enhance battery life while maintaining interrupt wake-up capability.
* **Analog Sensitivity Tuning** – Utilizing the **STM32 ADC (Analog-to-Digital Converter)** to calibrate smoke sensor threshold levels dynamically.

## 🎯 Why This Project?

* **Industrial Grade MCU** – Developed on the **ARM Cortex-M4**, a powerhouse chip used in automotive and industrial automation.
* **Interrupt-Driven Architecture** – Demonstrates a deep understanding of asynchronous event handling, a must-have for real-time systems.
* **Register-Level Programming** – Moves beyond HAL libraries to interact directly with hardware for maximum efficiency and control.

## 💡 Ideal For

* **Engineering Students** mastering ARM architecture and safety-critical system design.
* **Embedded System Designers** looking for fast, priority-based sensing prototypes.
* **STM32 Enthusiasts** exploring GPIO registers, EXTI handlers, and Seven-Segment multiplexing.

---
*Developed by: Azim Umar, Amir Asyraf, Melvin Jude, Tan Zi Long*
*Supervised by: Ir. Ts. Dr. Fauzan Khairi bin Che Harun*

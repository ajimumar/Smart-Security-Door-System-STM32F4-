# 🛡️ Smart Security Door System (STM32F4)
> **An Intelligent Home Security Solution featuring Priority-Based Sensing and Interrupt-Driven Alerts.**

---

## 🚀 Overview
Projek ini dibangunkan menggunakan mikropengawal **STM32F4** (Otak Kecil Board) dengan bahasa **C**. Ia direka untuk sistem keselamatan rumah pintar yang mampu mengesan asap (kebakaran) dan kehadiran manusia secara real-time. 

Sistem ini menggunakan **Bare-Metal Programming** (Register-level) untuk prestasi yang lebih laju dan efisien berbanding penggunaan library biasa.

---

## ✨ Key Features (Apa yang Gempak?)

* **🔥 Emergency Priority Logic** – Sistem secara automatik memberi keutamaan tertinggi kepada **MQ-2 Smoke Sensor**. Jika asap dikesan, semua fungsi lain akan dihentikan untuk memberi amaran kebakaran (F1).
* **👤 Smart Greeting System** – Menggunakan **FC-51 IR Sensor** untuk mengesan tetamu. Sistem akan memaparkan "H1" (Hi) pada Seven-Segment sebagai respon mesra pelanggan.
* **⚡ Instant Response Calling Bell** – Menggunakan **External Interrupt (EXTI1)** pada PB1. Buzzer akan berbunyi serta-merta bila butang ditekan tanpa sebarang *delay* dalam program utama.
* **📊 Dual 7-Segment Visualization** – Paparan status sistem yang jelas (F1 untuk Fire, H1 untuk Human) menggunakan konfigurasi GPIO yang dioptimumkan.

---

## 🛠️ Hardware Stack
* **Microcontroller:** STM32F446 (ARM Cortex-M4)
* **Sensors:** MQ-2 Smoke Sensor, FC-51 IR Obstacle Sensor
* **Actuators:** Active Buzzer, Dual 7-Segment Display, LED Array
* **Firmware:** C Language (Register-based)
* **IDE:** Keil uVision 5

---

## 📊 System Logic (Priority Table)

| Condition | Priority | Display | Buzzer | LED Status |
| :--- | :---: | :---: | :---: | :---: |
| **Smoke Detected** | 🔴 1 (Highest) | **F1** | Continuous | All ON |
| **Motion Detected** | 🟡 2 | **H1** | OFF | All ON |
| **Bell Pressed** | ⚡ Interrupt | - | Pulsed | - |
| **System Idle** | ⚪ 3 | (Blank) | OFF | All OFF |

---

## 🏗️ Program Architecture
Program ini disusun menggunakan **Subroutines** untuk memudahkan pengurusan kod:
* `buzzer_on()` & `buzzer_off()` - Kawalan amaran audio.
* `display_F1()` & `display_H1()` - Logik pemprosesan 7-Segment.
* `exti1_init()` - Konfigurasi interrupt untuk butang SW4.

---

## 👥 The Developers
* **Azim Umar** | **Amir Asyraf** | **Melvin Jude** | **Tan Zi Long**

---
*Project for Microprocessor (SKEE 3223) - Universiti Teknologi Malaysia*

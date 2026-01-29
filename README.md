# Smart-Security-Door-System-STM32F4-
This project is a microcontroller-based security system developed in C language using Keil uVision for the STM32F4 (Otak Kecil board). The system is designed to provide real-time monitoring and automated alerts for home security.
# Smart Security Door System (STM32F4)

## 1.0 Introduction
[cite_start]This project implements a microcontroller-based security system using C language in Keil uVision[cite: 15]. [cite_start]It features real-time monitoring using smoke and motion sensors, and an interrupt-driven calling bell[cite: 18].

## 2.0 Hardware Components
* [cite_start]**Microcontroller**: STM32F4 (Otak Kecil Board)[cite: 147].
* [cite_start]**Inputs**: MQ-2 Smoke Sensor, FC-51 Motion Sensor, and Push Button (SW4)[cite: 18, 147].
* [cite_start]**Outputs**: Dual Seven-Segment Display, LED indicators, and an Active Buzzer[cite: 19, 147].

## 3.0 System Logic
The system operates with specific priorities:
* [cite_start]**Fire Emergency**: If smoke is detected (highest priority), the buzzer sounds continuously, LEDs turn ON, and "F1" is displayed[cite: 41, 42].
* [cite_start]**Human Presence**: If motion is detected (without smoke), the display shows "H1" and LEDs turn ON[cite: 44].
* [cite_start]**Calling Bell**: The push button uses an External Interrupt (EXTI) to trigger the buzzer immediately when pressed[cite: 46, 47].

## 4.0 Circuit Diagram
[cite_start]*Designed using KiCad 9.0*[cite: 146].
(Insert your circuit image here!)

## 5.0 Program Structure
[cite_start]The program is developed using register-level GPIO configuration[cite: 20]. [cite_start]Subroutines are used for organized control[cite: 21]:
* [cite_start]`buzzer_on()` / `buzzer_off()` [cite: 160, 161]
* [cite_start]`leds_on()` / `leds_off()` [cite: 162, 163]
* [cite_start]`display_F1()` / `display_H1()` [cite: 164, 165]

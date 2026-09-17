# Hardware & Pinout Matrix

This document defines the electrical connections and power requirements for the Arduino Color Sorter and Robotic Arm (P03).

## Pinout Mapping [VERIFIED]
Extracted directly from the verified historical source code.

| Component | Terminal / Function | Arduino Pin | Notes |
| :--- | :--- | :--- | :--- |
| **TCS3200 Color Sensor** | S0 | D4 | Frequency scaling (High) |
| | S1 | D5 | Frequency scaling (Low) = 20% |
| | S2 | D6 | Color filter selection |
| | S3 | D7 | Color filter selection |
| | OUT | D8 | Frequency output read by `pulseIn()` |
| | VCC / GND | 5V / GND | Sensor power |
| **Micro Servos** | Base / Arm 1 | D9 | Base rotation / Primary arm |
| | Arm 2 | D10 | Secondary joint |
| | Arm 3 | D11 | Tertiary joint |
| | Claw 1 | D12 | Claw mechanism |
| | Claw 2 | D13 | Claw mechanism |
| **Indicator LEDs** | Red LED | A0 | Triggers on red block detection |
| | Yellow LED | A1 | Triggers on yellow/green block detection |
| | Blue LED | A2 | Triggers on blue block detection |

---

> [!WARNING]
> **CRITICAL POWER DISTRIBUTION NOTE**
> 
> Driving 5 micro servos simultaneously requires a significant current draw that **exceeds the limitations of the Arduino Uno's onboard 5V voltage regulator**. 
> 
> You MUST use an **external, dedicated 5V power supply** (e.g., a high-current battery pack or 5V 3A+ bench supply) to power the servos. The grounds between the external supply and the Arduino must be tied together. Attempting to power the servos directly from the Arduino's 5V rail will result in brownout resets, erratic robotic arm jitter, and potential damage to the microcontroller.

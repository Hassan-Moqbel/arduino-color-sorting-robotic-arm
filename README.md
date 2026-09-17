# P03: Arduino Color Sorter + Robotic Arm

## Project Overview
This project implements a pick-and-place mechatronic system utilizing an Arduino Uno. The system combines an articulated robotic arm (actuated by 5 micro servos) with a **TCS3200 color sensor** to automatically detect, classify, and sort colored objects. When an object is detected, the sensor measures the RGB frequency components. Once a valid color threshold is matched, the corresponding indicator LED illuminates, and the robotic arm initiates a pre-programmed kinematic sequence to grasp, move, and release the object into a designated sorting zone.

## System Bill of Materials (BOM)
*Derived from verified historical project documentation and code.*
- Microcontroller: Arduino Uno R3
- Color Sensor: TCS3200 (RGB frequency sensor)
- Actuation: 5x Micro Servos (e.g., SG90)
- Indicators: 3x LEDs (Red, Yellow, Blue)
- Hardware: Robotic arm chassis / 3D printed mechanical assembly

## TCS3200 Sensing Principle & Calibration
The TCS3200 utilizes a photodiode array with red, green, blue, and clear filters. The internal oscillator outputs a square wave whose frequency is directly proportional to the light intensity of the selected color.
- **Frequency Scaling**: The system sets `S0=HIGH` and `S1=LOW` to scale the output frequency to 20%, optimizing it for the Arduino's `pulseIn()` timing resolution.
- **Color Selection**: By toggling `S2` and `S3`, the firmware selectively reads the Red, Green, and Blue frequency responses.
- **Calibration**: The firmware relies on experimentally verified thresholds (e.g., matching a low frequency pulse width to high color intensity).

## Evidence Classification & Authenticity
- **Firmware / Source Code**: **[VERIFIED]** 
  The source code was successfully extracted verbatim from the original academic PDF report and has been formatted into the current `.ino` file. The logical thresholds and timing delays remain unaltered to preserve historical authenticity.
- **Documentation & Architecture**: **[RECONSTRUCTED]** 
  While the original report exists in the `docs/` directory, the Markdown-based repository structure, README summaries, and pinout matrices were compiled during portfolio enhancement to align with modern engineering standards.

# Marble Dropper & Water Volume Measurement System

A fully integrated mechanical, electrical, and software project built around a marble ramp and tank system. It automatically drops marbles into water, times their descent, counts them, and calculates their volume using water displacement—all displayed live on an LCD.

---

## 🎯 Project Summary

This project was designed as a capstone system for the **ECE 3720 Microprocessors** course at Oakland University. It showcases end-to-end integration between hardware construction, microcontroller programming, sensor interfacing, and signal processing.

**Core functions include:**

- **Stepper motor-controlled marble dropper**
- **IR beam sensors** for timing and marble counting
- **Water level sensor** for volume measurement
- **LCD display** for live output of time, volume, and count
- **Overflow safety system** to halt operations

---

## 🧠 System Design Overview

### 🔧 Hardware Components

- **Dragon12-Light Rev D Board** (with HCS12 MCU)
- **Unipolar Stepper Motor** for marble release
- **IR Sensors** (entry/exit detection on ramp)
- **eTape Water Level Sensor** (volume displacement)
- **16x2 LCD (HD44780)** for display
- **Custom Wood Frame** with neodymium magnets for modularity

### 🧰 Sensor Functions

| Sensor | Purpose |
|--------|---------|
| IR 1 (AN5) | Start timer when marble released |
| IR 2 (AN6) | Stop timer and increment count |
| Water Sensor (AN7) | Measure water level before/after marble drop |

---

## 🔄 Software Logic

- Uses **ATD (Analog-to-Digital Conversion)** to read analog sensors.
- Implements a **stepper motor control routine** to drop one marble per cycle.
- Calculates **marble volume by difference** in water level.
- Handles debounce logic to avoid double-counting.
- All values (volume, time, count) displayed in real-time on LCD.

---

## 📂 Files in `Marble_Dropper.zip`

- `main.c` – Main project code written in ANSI C for the HCS12 (Dragon12 board)
- `lcd.c / lcd.h` – Handles HD44780 LCD logic
- `stepper.c / stepper.h` – Stepper motor logic and control routines
- `sensor.c / sensor.h` – IR and water level sensor handling
- `makefile` – Compiling the project using CodeWarrior
- `Project_Final-Report.docx` – Engineering report and documentation
- `wiring_diagram.png` – (If included) Visual schematic of system wiring

---

## 📷 Key Visuals

- **Marble Rotor Mechanism**
- **Stepper Spinner Design**
- **IR Sensor Positions**
- **eTape Water Sensor**

---

## ⚠ Challenges Addressed

- **Stepper friction**: Resolved using ball bearings
- **Marble jamming**: Mitigated with rounded rotor corners
- **PWM/Delays**: Stepper motor implemented using delays (note: ideal use would be interrupts)
- **Sensor false reads**: IR threshold tuned manually to prevent noise

---

## 🔧 Limitations and Future Improvements

| Issue | Suggested Fix |
|-------|----------------|
| 8-bit ADC resolution | Upgrade to 10-bit for finer measurements |
| Delay-based stepper | Replace with interrupt-driven control |
| PVC water tank visibility | Use transparent vessel for better debugging |
| Basic IR sensors | Upgrade to Boolean edge-triggered sensors |
| LCD compatibility | Improve display to support higher bit resolution |

---

## 📜 References

1. *Mazidi & Causey*, *HCS12 Microcontroller and Embedded Systems*
2. Adafruit – [IR Sensor](https://www.adafruit.com/product/1031)
3. Adafruit – [eTape Water Sensor](https://www.adafruit.com/product/464)
4. Elegoo – [28BYJ-48 Stepper Motor](https://us.elegoo.com/products/)

---

## 🔒 License

For educational use only

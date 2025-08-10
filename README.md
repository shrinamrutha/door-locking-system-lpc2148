# Password-Based Door Lock System – LPC2148

[![Embedded C](https://img.shields.io/badge/Language-Embedded%20C-blue.svg)](https://en.wikipedia.org/wiki/Embedded_C)
[![Microcontroller](https://img.shields.io/badge/Hardware-LPC2148-green.svg)](https://www.nxp.com/products/processors-and-microcontrollers/arm-microcontrollers/general-purpose-mcus/lpc2000-arm7)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)
[![Secure Access](https://img.shields.io/badge/Security-Password%20Protected-brightgreen)](#features)

---

## 📌 Overview

This project implements a **Password-Based Door Lock System** using the **LPC2148 ARM7 microcontroller**.
The system enhances **home and business security** by requiring a **4-digit password** for door access.
If the correct password is entered, the door unlocks via a **DC motor**, otherwise an **ACCESS DENIED** message is shown.

---

## ✨ Features

* 🔐 **Password Protection** – Only authorized users can access.
* 🖥 **16x2 LCD Display** – Displays prompts and access status.
* 🎛 **4x3 Keypad** – User-friendly password entry.
* ⚙️ **Motorized Lock** – DC motor opens/closes the door.
* 📂 **Multiple Users** – Stores up to **20 usernames and passwords**.

---

## 🏗 System Block Diagram

```
 ┌──────────────┐
 │ 4x3 Keypad   │
 └─────┬────────┘
       │
 ┌─────▼─────────┐
 │  LPC2148 MCU  │
 │ - Input Scan  │
 │ - Password    │
 │   Validation  │
 │ - Motor Ctrl  │
 │ - LCD Output  │
 └─────┬─────────┘
       │
 ┌─────▼─────────┐
 │  L293D Motor  │
 │    Driver     │
 └─────┬─────────┘
       │
 ┌─────▼─────────┐
 │   DC Motor    │
 │  (Door Lock)  │
 └───────────────┘

 LCD Display <── MCU ──> EEPROM (User Data)
```

---

## 🛠 Technologies Used

### **Hardware**

* **Microcontroller** – LPC2148 ARM7
* **Input Device** – 4x3 Matrix Keypad
* **Display** – 16x2 LCD
* **Motor Driver** – L293D
* **Actuator** – DC Motor
* **Power Supply** – 5V/12V

### **Software**

* Embedded C (Keil µVision / ARM GCC)
* LCD Interface Functions
* Keypad Scanning Algorithm
* Motor Control Logic
* Password Matching Routine

---

## 📂 Functional Modules

1. **Initialization** – Configures I/O pins, LCD, and keypad.
2. **Password Input** – Reads 4 digits from keypad (masked with `*`).
3. **Validation** – Compares entered password with stored credentials.
4. **Door Control**

   * **Correct Password** → Display “ACCESS GRANTED” & rotate motor forward.
   * **Incorrect Password** → Display “ACCESS DENIED”.
5. **Motor Reversal** – Closes the door after delay.

---

## 📊 Performance

| Parameter       | Value      |
| --------------- | ---------- |
| Max Users       | 20         |
| Password Length | 4 digits   |
| MCU Clock       | 60 MHz     |
| Response Time   | < 1 second |

---

## 🚀 Installation & Usage

### **Hardware Setup**

1. Connect **4x3 Keypad** to LPC2148 GPIO pins.
2. Connect **LCD** to Port 0 pins.
3. Interface **L293D Motor Driver** with MCU and DC motor.
4. Provide power supply to MCU & motor driver.

### **Software Setup**

1. Open the code in **Keil µVision** or your preferred ARM development IDE.
2. Compile and load the program into LPC2148 via Flash Programmer.
3. Run the system and enter passwords via keypad.

---

## 📄 Requirements

```
Keil µVision / ARM GCC Toolchain
Flash Magic / LPC Programmer
LPC2148 Development Board
4x3 Matrix Keypad
16x2 LCD
L293D Motor Driver
DC Motor
```

---

## 📚 References

* LPC2148 ARM7 Datasheet – NXP
* LCD Interfacing with ARM Microcontrollers
* Keypad Scanning Techniques in Embedded Systems

---

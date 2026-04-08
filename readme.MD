# 📡 STM32 Bluetooth LED Control (UART Interrupt)

## 📌 Project Overview
This project demonstrates how to control an LED using a Bluetooth module (HC-05/HC-06) with an STM32 microcontroller via UART communication in interrupt mode.

A mobile app (Arduino Bluetooth Controller) is used to send commands wirelessly to the STM32, which then turns an LED ON or OFF.

---

## ⚙️ Features
- UART communication using interrupts
- Real-time LED control via Bluetooth
- Lightweight and efficient embedded C code using HAL drivers
- Simple command-based control system

---

## 🧰 Hardware Requirements
- STM32 Microcontroller (e.g., Nucleo / Discovery board)
- HC-05 Bluetooth Module
- LED (or onboard LED)
- Resistor (220Ω recommended)
- Jumper wires
- Mobile phone with Bluetooth

---

## 🔌 Circuit Connections

| Bluetooth Module | STM32 |
|----------------|--------|
| VCC            |  3.3V |
| GND            | GND |
| TX             | USART1_RX (e.g., PA10) |
| RX             | USART1_TX (e.g., PA9)  |



---

## 📱 Mobile App
- App Used: **Arduino Bluetooth Controller**
- Connect to HC-05 device
- Send:
  - `Y` → Turn LED ON
  - `N` → Turn LED OFF

---

## 💻 Software Details

### UART Configuration
- Baud Rate: `9600` (default for HC-05)
- Data Bits: 8
- Stop Bits: 1
- Parity: None
- Mode: TX/RX with Interrupt

---

## 🧠 Working Principle

1. STM32 initializes UART in interrupt mode.
2. Bluetooth module receives data from mobile app.
3. Data is forwarded via UART to STM32.
4. Interrupt callback (`HAL_UART_RxCpltCallback`) is triggered.
5. Based on received character:
   - `'Y'` → LED ON
   - `'N'` → LED OFF
6. UART interrupt is re-enabled for continuous reception.

---



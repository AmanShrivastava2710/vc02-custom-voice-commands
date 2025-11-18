# VC-02 Custom Offline Voice Command Project

This repository demonstrates how to create, train, flash, and use **custom offline voice commands** on the **VC-02 Voice Recognition Module (US516P6-based)**.  
The setup and workflow are based on the tutorial **“Add Custom Voice Command to your Projects using VC-02 Module”** by Aviyan’s Thoughts.

This project covers firmware generation, command configuration, hardware wiring, and microcontroller integration.

---

## 📌 Features

- Fully offline voice recognition (no internet required)  
- Create custom wake words  
- Add up to **150 custom commands**  
- Select built-in voice responses  
- Generate custom firmware using AI-Thinker/Unisound online tool  
- Flash firmware through UART  
- Control hardware through GPIO or UART  
- Compatible with Arduino, ESP32, Raspberry Pi Pico, etc.

---

## 🧩 Hardware Requirements

- VC-02 Module (US516P6 chip)  
- VC-02 Development Kit / Breakout board (recommended)  
- CH340 USB-to-UART (if not included on the board)  
- Microphone (onboard or external)  
- Speaker  
- 3.3V or 5V power source  
- Jumper wires  
- Optional: Arduino / ESP32 / MCU board

---

## ⚙️ Technical Specifications

| Feature | Details |
|--------|---------|
| **Chipset** | Unisound US516P6 (32-bit RISC) |
| **Flash** | 2 MB |
| **SRAM** | 242 KB |
| **Interfaces** | UART, GPIO, I2C, PWM, ADC |
| **Supported Languages** | English, Chinese |
| **Max Commands** | ~150 |
| **Operating Voltage** | 3.3V – 5V |

---

## 🚀 Setup Steps

1. Register/Login on the **AI-Thinker / Unisound VC-02 Online Firmware Tool**.  
2. Create a new **Scene** for your project.  
3. Add a **custom wake word** (optional).  
4. Add **custom commands** and define their actions / module replies.  
5. Adjust settings:  
   - Timeout  
   - Command groups  
   - System responses  
6. Generate and **download the custom firmware (.bin)**.  
7. Use the VC-02 Burning Tool to **flash the firmware** via UART (CH340).  
8. Reset the module at the correct moment when flashing starts.  
9. Connect hardware (speaker, mic, UART, GPIO).  
10. Test commands and integrate with Arduino/ESP32.

---

## 🔥 Firmware Flashing

### Required Tools
- VC-02 Burning Tool (Windows/Linux)
- CH340 USB-to-UART driver
- Custom `.bin` firmware file

### Common Issues

- Incorrect **reset timing** → flashing fails  
- Custom firmware may override **default UART behavior**  
- Bad firmware flash can temporarily **brick the module**

---

## 🔌 Wiring Overview

| VC-02 Pin | Connects To | Description |
|----------|--------------|-------------|
| VCC | 3.3V / 5V | Power |
| GND | Ground | – |
| TX | MCU RX | Module → MCU |
| RX | MCU TX | MCU → Module |
| SPK+ / SPK- | Speaker | Audio output |
| MIC+ / MIC- | Microphone | Audio input |
| GPIOs | Relays, LEDs, motors | Activated after recognition |

> **Note:** GPIO mode allows direct control of appliances without a microcontroller.

---

## 📘 Example Use Cases

- Voice-controlled home automation  
- Voice-activated robots  
- Contactless switches  
- IoT devices without internet  
- Assistive voice systems  

---

## ⚠️ Known Limitations

- Sensitive to background noise  
- Flashing requires correct reset timing  
- Limited built-in voice responses  
- Very long command phrases reduce detection accuracy  

---

## 📁 Repository Structure

VC-02-Custom-Voice-Commands
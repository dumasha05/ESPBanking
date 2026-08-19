<div align="center">

# 🏦 ESPBank Simulator

**A standalone banking simulator & captive web portal running entirely on an ESP32 microcontroller!** 🚀

[![ESP32](https://img.shields.io/badge/Microcontroller-ESP32-red.svg?style=for-the-badge&logo=espressif)](https://www.espressif.com/)
[![Language](https://img.shields.io/badge/Language-C%2B%2B-blue.svg?style=for-the-badge&logo=cplusplus)](https://isocpp.org/)

[![Status](https://img.shields.io/badge/Status-Active-brightgreen.svg?style=for-the-badge)](#)

---

[Editions](#-version-matrix--editions) • [Environment](#%EF%B8%8F-environment--library-requirements-pro--ultra-pro) • [Flashing Guide](#-free-edition-binary-flashing-guide) • [Hardware Wiring](#-hardware-wiring--pinouts) • [Support](#-community--support)

</div>

---

## 🌟 Overview

Welcome to the official repository for **ESPBank Simulator** — an all-in-one standalone banking simulator and captive portal web environment powered by the ESP32! Designed for testing, hardware integrations, and custom web portal demonstrations.

---

## 📦 Version Matrix & Editions

We offer three distinct editions to suit your hardware setup and feature requirements:

| Feature / Capability | 🟢 **Free Edition** | 🔵 **Pro Edition** | 🟣 **Ultra Pro Edition** |
| :--- | :---: | :---: | :---: |
| **Format** | Compiled Binary (`.bin`) | Arduino Sketch (`.ino`) | Arduino Sketch (`.ino`) |
| **Captive Web Portal** | Core Local Web UI | Modern Responsive Web UI | Modern Responsive Web UI |
| **Display Support (TFT UI)** | ✅ ST7789 Integration | ✅ ST7789 Integration | ✅ ST7789 Integration |
| **Security Features** | Standard Protection | Advanced Security | Advanced Security |
| **Serial Diagnostics** | ❌ | ❌ | ✅ Serial Monitor Logs |
| **RFID Module Access** | ❌ | ❌ | ✅ Full RFID Access |
| **Source Code Protection** | Binary Protected | Full `.ino` Source | Full `.ino` Source |
| **Access / Link** | **Included in Releases** | [🛒 **Get Pro Version**](https://buy.polar.sh/polar_cl_0bKVXNPvRLxRmi2gwR9kSxV05FBdRlY7aQK0i4DmsnZ) | [⚡ **Get Ultra Pro Version**](https://buy.polar.sh/polar_cl_ccz5OsXlkcnZDQX2rKivadVrn4bEla0S8CP6v3TzJnK) |

---

## 🛠️ Environment & Library Requirements (Pro & Ultra Pro)

To compile the Arduino sketches (`.ino`) successfully without memory or build errors, ensure your Arduino IDE environment matches these specifications:

> [!IMPORTANT]
> **Required Driver Notice:** Always use direct **Adafruit GFX** and **ST7789** drivers. **Never use `TFT_eSPI`**.

* 🧠 **ESP32 Arduino Core:** Version `2.0.14`
* 🌐 **ESPAsyncWebServer:** Version `1.2.3` *(by ESPAsync)*
* ⚡ **AsyncTCP:** Version `1.1.4`
* 📺 **Display Drivers:** Direct `Adafruit GFX` & `ST7789`
* 💾 **Partition Scheme:** Must be set to **`Huge APP (3MB No OTA / 1MB SPIFFS)`**
  * *Location:* `Tools > Partition Scheme > Huge APP (3MB No OTA / 1MB SPIFFS)`
  * *(Standard partition layouts lack the flash space required for embedded web assets and program logic).*

---

## ⚡ Free Edition: Binary Flashing Guide

The **Free Edition** is distributed as a pre-compiled binary (`.bin`) to protect source architecture. Flash it directly to your ESP32 using `esptool`:

### Step 1: Install `esptool`
Ensure Python is installed on your computer, then install `esptool` via command prompt / terminal:

    py -m pip install esptool

### Step 2: Connect Your Hardware
Connect your ESP32 using a quality USB data cable and identify your COM port (e.g., `COM3` on Windows or `/dev/ttyUSB0` on Linux/Mac).

### Step 3: Run Flash Command
Execute the following command *(update `COM3` and your binary filename as needed)*:

    python -m esptool --chip esp32 --port COM3 --baud 921600 write_flash -z 0x1000 espbank_free_v1.bin

> [!TIP]
> **Connection Hangs?** If `esptool` gets stuck attempting to connect, press and hold the physical **BOOT** button on your ESP32 board until the flashing progress begins!

---

## 🔌 Hardware Wiring & Pinouts

### 🖥️ 1. Pro Edition Display Connections (ST7789 TFT SPI)

| ESP32 Pin | Display Pin | Description |
| :--- | :--- | :--- |
| **GPIO 23** | `SDA` / `MOSI` | SPI Data Line |
| **GPIO 18** | `SCL` / `SCK` | SPI Clock Line |
| **GPIO 5** | `CS` | Chip Select |
| **GPIO 22** | `DC` / `RS` | Data / Command Control |
| **GPIO 21** | `RES` / `RST` | Display Reset |

---

### 💳 2. Ultra Pro Edition: RFID Reader Wiring

> [!WARNING]
> **Wiring Quirk Note:** In this tested hardware configuration, the RFID reader **IRQ pin** is intentionally left unconnected and is linked directly to the reset and `EN` pins as verified in working setups.

| RFID Module Pin | ESP32 Pin | Notes |
| :--- | :--- | :--- |
| **SDA (SS)** | **GPIO 4** | SPI Slave Select |
| **SCK** | **GPIO 18** | Shared SPI Clock |
| **MOSI** | **GPIO 23** | Shared SPI MOSI |
| **MISO** | **GPIO 19** | Shared SPI MISO |

---

## 💬 Community & Discussions

Join my Blog at https://dev.to/dumasha_01f08bc176b77172f/espbanking-by-dumasha-12ma

---

## 📧 Contact & Support

Have questions or need custom hardware/software support? Feel free to reach out directly:

* **Developer:** Dumasha Wijesekeragamage
* **Email:** [dumasha05@gmail.com](mailto:dumasha05@gmail.com)

---

## ⚖️ License
Copyright (c) 2026 ESPBanking. All rights reserved.

1. RESTRICTIONS
You are strictly prohibited from modifying, adapting, reverse engineering, decompiling, disassembling, or creating derivative works of this source code or compiled firmware. 

2. PERSONAL USE
You are granted a non-exclusive, non-transferable license to use the software for strictly personal, non-commercial purposes only.

3. COMMERCIAL USE PROHIBITED
Any commercial use, business deployment, redistribution, or inclusion of this software in products intended for sale requires prior written authorization and a commercial agreement. To acquire a commercial license, you must contact the author directly.

4. DISCLAIMER
THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED.
---

<div align="center">
  <sub>Crafted with ❤️ for ESP32 Enthusiasts & Developers</sub>
</div>

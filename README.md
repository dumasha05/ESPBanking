# 🏦 ESPBanking - ESP32 Standalone Offline Banking Server

[![Buy on Polar](https://img.shields.io/badge/Polar-Download_Code_%26_Manual-blue?style=for-the-badge&logo=polar)](https://buy.polar.sh/polar_cl_0bKVXNPvRLxRmi2gwR9kSxV05FBdRlY7aQK0i4DmsnZ)
[![Reddit Discussion](https://img.shields.io/badge/Reddit-Discuss_on_r%2Fesp32projects-FF4500?style=for-the-badge&logo=reddit)](https://www.reddit.com/r/esp32projects/comments/1vgzaix/i_built_a_standalone_offline_banking_server/)
[![Hardware](https://img.shields.io/badge/Hardware-ESP32_%7C_ST7789-orange?style=for-the-badge)](https://github.com/dumasha05/ESPBBanking1)
[![License](https://img.shields.io/badge/License-Proprietary-red?style=for-the-badge)](https://buy.polar.sh/polar_cl_0bKVXNPvRLxRmi2gwR9kSxV05FBdRlY7aQK0i4DmsnZ)

A completely self-contained, zero-cloud financial server running on a single ESP32 microcontroller with an ST7789 TFT display and an embedded dark-mode web dashboard.

---

## 📺 Technical Showcase & Live Demo

[![ESPBanking Hardware Demo](https://img.youtube.com/vi/rb28To7py64/maxresdefault.jpg)](https://www.youtube.com/watch?v=rb28To7py64)  
*Click above to watch the ESPBanking technical demonstration on YouTube!*

---

## 📌 Project Overview

ESPBanking transforms an ESP32 into a standalone micro-server that operates 100% offline—no cloud dependencies, external databases, or active internet connections required.

Once powered up, the ESP32 connects to local Wi-Fi and serves a full-featured single-page web app directly from its internal flash memory to any browser on your network.

---

## 💬 Community & Discussion

* **Reddit Post:** Read the project announcement and join the technical discussion on [r/esp32projects](https://www.reddit.com/r/esp32projects/comments/1vgzaix/i_built_a_standalone_offline_banking_server/).

---

## 🛠️ Hardware Requirements & Wiring Pinout

| Component | Display Pin | ESP32 GPIO | Function / Signal Description |
| :--- | :--- | :--- | :--- |
| **ST7789 TFT Display (2.4")** | **CS** | `GPIO 15` | Chip Select |
| | **DC** | `GPIO 2` | Data / Command Toggle |
| | **RST** | `GPIO 4` | Hardware Reset |
| | **SCL / SCK** | `GPIO 18` | SPI Clock Line |
| | **SDA / MOSI** | `GPIO 23` | SPI Data Line |
| **Arduino IDE Config** | **Partition** | `Huge APP` | `3MB No OTA / 1MB SPIFFS/LittleFS` |

---

## ✨ Key Features

* **📱 Embedded Dark-Mode Web Dashboard:** Serves a responsive web application directly from flash memory (`PROGMEM`) to mobile devices or desktop browsers.
* **👥 Dual-Role System (User & Admin):**
  * **User Panel:** Check account balances, perform transfers, log expenses, and pay active bills.
  * **Admin Panel:** Account creation/freezing, manual balance adjustments, global announcements, tax & interest rate controls, and LittleFS database backups.
* **🖥️ Differential TFT Display Engine:** Drives an attached ST7789 SPI screen with localized differential rendering to deliver crisp, flicker-free status updates.
* **🔒 Embedded Security Engine:** Built with SHA-256 password hashing, hardware-generated session tokens (`esp_random`), sliding session timeouts, and rate-limited brute-force account lockouts.
* **💾 Persistent Local Storage:** Keeps user accounts, settings, and logs saved directly on onboard flash using the LittleFS file system with wear leveling and power-loss protection.
* **🧮 Fixed-Point Precision Accounting:** Avoids decimal floating-point rounding bugs by processing transactions using 64-bit integer calculations.

---

## 💡 Why Purchase the Full Bundle?

Building a zero-cloud banking node from scratch requires **15+ hours** of FreeRTOS task management, memory allocation, and differential SPI rendering setup. 

| Feature | DIY Scratch Build | ESPBanking Production Bundle ($19) |
| :--- | :---: | :---: |
| **Library Version Verification** | Build Errors / Version Mismatches | Pre-verified (`ESPAsyncWebServer 3.12.0`, `ArduinoJson 7.4.3`) |
| **Accounting Precision** | Rounding Bug Risk | 64-Bit Fixed Integer Cents Engine |
| **Documentation & Pinout** | Hours of Trial & Error | Complete Setup & Operations Manual Included |
| **Web Assets in Flash** | Memory Overflows | Pre-compiled Dark-Mode Single Page Application |

---

## 🚀 Get the Complete Source Code & Manual

The full production-ready `.ino` source file and comprehensive setup manual (including full wiring schematics and library configuration guides) are available for instant download:

👉 **[Click Here to Download Source Code & Manual on Polar](https://buy.polar.sh/polar_cl_0bKVXNPvRLxRmi2gwR9kSxV05FBdRlY7aQK0i4DmsnZ)**

### Package Contents:
* **`ESPBanking.ino`** – Complete, pre-configured source code.
* **`ESPBanking_System_Manual.docx`** – Complete pin wiring table, setup guide, default credentials, and operational instructions.

---

## 📄 Intellectual Property & Licensing Notice

© 2026 ESPBanking. All rights reserved.

### Terms of Use & Commercial Policy
* **Proprietary Software:** The source code, embedded web interfaces, display algorithms, and documentation associated with ESPBanking are proprietary software.
* **Personal License:** Purchase of the source code grants you a non-exclusive, non-transferable license for personal, educational, and internal testing use only.
* **Prohibited Actions:** You may NOT redistribute, resell, re-license, host public mirror repositories, or publicly re-upload the source code (`.ino`) or documentation files in whole or in part without prior written permission.
* **DMCA Enforcement:** Unauthorized distribution or commercial exploitation of this codebase will result in immediate DMCA takedown requests and copyright infringement reports.

---

## 📬 Support & Contact

* **Email:** `dumasha05@gmail.com`
* **GitHub Repository:** [github.com/dumasha05/ESPBBanking1](https://github.com/dumasha05/ESPBBanking1)

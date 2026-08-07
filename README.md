# 🏦 ESPBanking System (Free & Pro Editions)

An embedded, local web-based banking and account simulation system designed for the **ESP32** microcontroller, featuring real-time visual feedback via an **ST7789 TFT Display**.

Created by **Dumasha**.

---

## 📬 Contact & Community
* **Email:** dumasha.contact@gmail.com
* **Reddit Discussion:** [Check out the r/esp32projects thread](https://www.reddit.com/r/esp32projects/comments/1vgzaix/i_built_a_standalone_offline_banking_server/)

---

## 📋 Table of Contents
- [Free Edition (Lite)](#-free-edition-lite)
- [Pro Edition ($15)](#-pro-edition-15)
- [Hardware Wiring & Pin Configuration](#-hardware-wiring--pin-configuration-st7789-spi)
- [Quick Start Guide](#-quick-start-guide)

---

## 🟢 Free Edition (Lite)

The Free Edition provides a fully functional, standalone local application designed for hobbyists and makers.

### Features
* **Local Web Dashboard:** Clean, responsive HTML/JS web interface served directly from the ESP32.
* **TFT Display Status Monitor:** Live screen updates showing system boot state, Wi-Fi connection status, local IP address, and active user session.
* **Capped User System:** Manages up to 3 local accounts (`admin`, `alice`, `bob`).
* **Transactions:** Real-time deposit and withdrawal logic tracking cent-precision values with a running history log.
* **Serial Wi-Fi Provisioning:** Easily configure network credentials dynamically via the Arduino Serial Monitor.

---

## 💎 Pro Edition ($15)

Unlock the full power of ESPBanking for advanced deployments and professional setups. 

### Pro Features Include:
* **Advanced Security Suite:** SSL/TLS encrypted HTTPS connections, automated session timeouts, and multi-factor authentication.
* **Extended User Management:** Remove the 3-account restriction to support a scalable directory of users and administrative roles.
* **Persistent Database Integration:** Enhanced backend storage utilizing LittleFS/SPIFFS with encrypted JSON database structures.
* **Priority Updates & Support:** Direct access to code updates, security patches, and developer assistance.

---

### 🛒 Upgrade to Pro
[![Upgrade to ESPBanking Pro](https://img.shields.io/badge/Upgrade_to-ESPBanking_Pro_($15)-orange?style=for-the-badge&logo=buymecoffee&logoColor=white)](https://buy.polar.sh/polar_cl_0bKVXNPvRLxRmi2gwR9kSxV05FBdRlY7aQK0i4DmsnZ)

---

## 🛠️ Hardware & Pin Configuration (ST7789 SPI)

| Pin Function | ESP32 GPIO Pin |
| :--- | :--- |
| **TFT_CS** | GPIO 15 |
| **TFT_DC** | GPIO 2 |
| **TFT_RST** | GPIO 4 |
| **TFT_MOSI (SDA)** | GPIO 23 |
| **TFT_SCLK (SCL)** | GPIO 18 |

---

## 🚀 Quick Start Guide (Free Edition)
  There is also a Manual Available for your convinience

1. Clone or download this repository.
2. Open `ESPBanking_Free.ino` in the **Arduino IDE**.
3. Install required library dependencies:
   * `Adafruit GFX Library`
   * `Adafruit ST7789 Library`
4. Select your ESP32 board configurations and flash the code.
5. Open the **Serial Monitor (115200 baud)**. If no Wi-Fi credentials are saved, the device creates an Access Point named **`ESPBank-Local`** (Password: `12345678`) or you can provision via serial:
   ```text
   WIFI:YourSSID,YourPassword
   

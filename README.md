# 🏦 ESPBanking System (Free & Pro Editions)

**Made by Dumasha**

An embedded, local web-based banking and account simulation system designed for the **ESP32** microcontroller, featuring real-time visual feedback via an **ST7789 TFT Display**.

---

## 📬 Contact & Community
* **Email:** dumasha.contact@gmail.com
* **Reddit Discussion:** [r/esp32projects Thread](https://www.reddit.com/r/esp32projects/comments/1vgzaix/i_built_a_standalone_offline_banking_server/)

---

## 💎 Pro Edition ($15)

Unlock the full power of ESPBanking for advanced deployments and professional setups. Features include advanced security (SSL/TLS), unlimited user slots, and encrypted database integration.

**Purchase ESPBanking Pro Here:**
[https://buy.polar.sh/polar_cl_0bKVXNPvRLxRmi2gwR9kSxV05FBdRlY7aQK0i4DmsnZ](https://buy.polar.sh/polar_cl_0bKVXNPvRLxRmi2gwR9kSxV05FBdRlY7aQK0i4DmsnZ)

---

## 🟢 Free Edition (Lite)

The Free Edition provides a fully functional, standalone local application designed for hobbyists and makers. It features a capped 3-user system, basic transaction logic, and real-time ST7789 TFT display monitoring.

### 🛠️ Hardware & Pin Configuration (ST7789 SPI)

| Pin Function | ESP32 GPIO Pin |
| :--- | :--- |
| **TFT_CS** | GPIO 15 |
| **TFT_DC** | GPIO 2 |
| **TFT_RST** | GPIO 4 |
| **TFT_MOSI (SDA)** | GPIO 23 |
| **TFT_SCLK (SCL)** | GPIO 18 |

---

## 🚀 How to Download `esptool` & Flash the Binary

`esptool` is the official Python utility used to flash firmware to ESP32 chips. Follow these steps to upload the Free Edition binary to your board.

### 1. Download & Install `esptool`
Open your command prompt or terminal and install the tool using Python:
```bash
py -m pip install esptool
```

### 2. Connect Your ESP32
Plug your ESP32 into your computer using a data-capable USB cable. Note the assigned COM port (e.g., `COM3` on Windows, or `/dev/ttyUSB0` on Linux/Mac). Put the board into download mode if required by holding the **BOOT** button, pressing **RST**, and releasing **BOOT**.

### 3. Erase Flash Memory (Recommended)
Wipe any old data to prevent boot loops. Replace `COM3` with your actual port:
```bash
py -m esptool --chip esp32 --port COM3 erase_flash
```

### 4. Flash the Firmware Binary
Upload the compiled binary. 

*If you are using a single merged binary file:*
```bash
py -m esptool --chip esp32 --port COM3 --baud 921600 write_flash 0x0 espbanking_free_merged.bin
```

*If you are using separate component binaries (Bootloader, Partitions, and App):*
```bash
py -m esptool --chip esp32 --port COM3 --baud 921600 write_flash 0x1000 bootloader.bin 0x8000 partitions.bin 0x10000 espbanking_free.bin
```

### 5. Wi-Fi Provisioning & Startup
Open your Serial Monitor at **115200 baud**. If no network credentials are saved, the ESP32 will host an Access Point named **`ESPBank-Local`** (Password: `12345678`). You can also provision it directly via the serial terminal by sending:
```text
WIFI:YourSSID,YourPassword
```
Once connected, navigate to the assigned IP address shown on the TFT screen to access the dashboard.

---

## ⚖️ License & Copyright

**© 2026 Dumasha. All Rights Reserved.**

This software is the intellectual property of Dumasha. You are permitted to download and use the Free Edition for personal, non-commercial purposes. 

**Restrictions:**
* **No Copying or Stealing:** You may not copy, reverse-engineer, modify, distribute, or re-upload this code or binary as your own work.
* **No Commercial Use:** You may not sell or monetize this software in any form.
* **Pro Edition:** The Pro version is strictly for the original purchaser and cannot be shared or redistributed.

By downloading or using this software, you agree to these terms.

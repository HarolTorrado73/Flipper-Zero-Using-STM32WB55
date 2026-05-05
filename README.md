# DIY Flipper Zero with STM32WB55

A cheap and affordable alternative to the original Flipper Zero, built from scratch using an STM32WB55CGU6 microcontroller.

This project is built for **learning and educational purposes**, focusing on embedded systems, RF modules, and custom firmware installation. I cover the hardware setup, OTP configuration, and firmware installation process step by step.

---

## Hardware Used

| Component | Description |
|-----------|-------------|
| STM32WB55CGU6 board | Main microcontroller with BLE 5.0 support |
| CC1101 Module | Sub-GHz RF transceiver |
| 1.4" 128x64 ST7565 LCD | Display module |
| Micro SD Card Module | External storage for apps and assets |
| Push Buttons (x6) | User input controls |
| Li-ion Battery | Rechargeable power source |

## 3D Printed Case

The `stl/` folder contains the 3D models for the enclosure:
- `BASE.stl` -- Base of the case
- `avanze1.stl` -- Front panel
- `avanze2-con-logo.stl` -- Front panel with logo
- `logo-kintrax.stl` -- Custom logo
- `Untitled.stl` -- Additional part

---

## Software Prerequisites

Before starting, you need to download and install the following software:

### 1. STM32CubeProgrammer (required)

Tool used to flash the firmware and OTP data onto the STM32WB55.

- **Version**: 2.22.0 (Win64)
- **Download**: [STM32CubeProgrammer - st.com](https://www.st.com/en/development-tools/stm32cubeprog.html)

> **Note**: You need to create a free account on st.com to download this software.

### 2. Flipper Zero Firmware & qFlipper (reference)

For firmware updates and device management.

- **Download**: [Flipper Downloads Page](https://flipper.net/pages/downloads)

---

## Step-by-Step Guide

### Step 1: Install STM32CubeProgrammer

1. Go to [st.com/en/development-tools/stm32cubeprog.html](https://www.st.com/en/development-tools/stm32cubeprog.html)
2. Create an account or log in
3. Download **STM32CubePrg-W64** version 2.22.0 (for Windows 11)
4. Run the installer and follow the setup wizard

### Step 2: Enter Boot Mode and Connect

1. Open **STM32CubeProgrammer**
2. On the STM32WB55 board, **press and hold the BOOT button**
3. While holding BOOT, **connect the board to your PC via USB**
4. Open **Device Manager** (Win + X > Device Manager) and verify the device appears correctly
5. In STM32CubeProgrammer, select the USB connection and click **Connect**

> More steps coming soon...

---

## Repository Structure

```
stm/
├── DIY Flipper/
│   ├── Firmware/          # Flipper firmware (.dfu)
│   ├── OTP/               # OTP binary files and addresses
│   └── SD Card/           # SD card contents (apps, assets, configs)
├── stl/                   # 3D printable case models
├── .gitignore
└── README.md
```

---

## OTP Configuration

The STM32WB55 requires OTP (One-Time Programmable) data to be written:

| OTP Region | Address |
|------------|---------|
| First OTP  | `0x1FFF7000` |
| Second OTP | `0x1FFF7010` |

The binary files for flashing are located in `DIY Flipper/OTP/`:
- `First_otp.bin`
- `Second OTP.bin`

---

## Disclaimer

This project is for **educational purposes only**. I am not responsible for any misuse. Always comply with local laws and regulations regarding RF transmission and electronic devices.

## License

This project is shared for educational use. The Flipper Zero firmware is licensed under [GPLv3](https://github.com/flipperdevices/flipperzero-firmware/blob/dev/LICENSE).

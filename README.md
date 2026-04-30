# LED Beacon 🚀
> Upgrading cheap beacons for professional DMX/Art-Net stage control.

![Hardware Render](./docs/render.png) <!-- Tip: Export a nice 3D render from KiCAD -->

## 🚀 Manufacturing Status
- [ ] **Design:** Completed
- [ ] **Prototyping:** In Progress
- [ ] **Production:** Pending


## 📋 Quick Specs
- **MCU:** ESP32-C3-WROOM-02
- **Power:** +12V ±30% @ 2A
- **Connectivity:** DMX512 via 5 pin XLRs and WiFi

## 📂 Project Structure
- `/hardware`: KiCAD project files (Version 9.0.7).
- `/firmware`: PlatformIO project (Arduino/ESP-IDF framework).
- `/mechanical`: 3D-printable housing (.STEP).
- `/docs`: Specification, schematics and design calculations.
<!-- test: for test scripts -->

## 🛠 Setup & Development

### Hardware
- **Library Dependencies:** All footprints/symbols are [local to the repo / use standard KiCAD libs].
- **CI/CD:** Schematics are automatically exported to `/docs` on every push.

### Firmware
1. Open the `/firmware` folder in **VS Code**.
2. Ensure the **PlatformIO** extension is installed.
3. Connect your hardware via USB C port and click **Upload**.

## User Guide

1. apply power via DC connector, 12V ±30% from a 3A capable supply.
2. attach to DMX bus with 2x XLR 5pin cables
  a) if at the end of the bus use a terminator plug
3. select a DMX address
  a) this light consumes 20 slots so avoid address above 492.
  b) ensure that this light is >20 slots away from the next lights.
4. Disable the WiFi AP unless needed for diagnostics
5. Use your DMX controller to send packets on the DMX bus.
  a) slots 1 to 10 control the brightness, 0x00 is off, 0xFF is on
  b) slots 11 to 20 control the strobe effect, 0x00 is fully on, 0x01 strobes at 0.2Hz, 0xFF strobes at 20Hz.
6. Enjoy!

---
*Commissioned for Null Sector for EMF Camp 2026.*

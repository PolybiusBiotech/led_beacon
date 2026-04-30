# LED Beacon: Technical Specification

The goal is to create a PCB that allows cheap LED Beacons to be upgraded so they can be controlled with a typical stage lighting desk.

Using the [MoSCoW method](https://en.wikipedia.org/wiki/MoSCoW_method) to prioritise specifications.

## 1. Must Have
*   **10-Channel Control:** Independent PWM control for 10x 6.4V @ 0.3A LED strips.
*   **DMX512-A Input:** 5-pin XLR interface with 5kV galvanic isolation and TVS protection.
*   **Robust Power Input:** Operation between +12V DC ±30% (8.4V – 15.6V).
*   **Strobe Functionality:** Support for 0.2Hz to 20Hz strobe speeds via DMX512.
  *   `0x00`: Static ON
  *   `0x01`: 0.2Hz Strobe.
  *   `0xFF`: 30Hz Strobe.
*   **Gamma Correction:** Implementation of a gamma brightness curve for human-eye linearity of LED PWM.
*   **Weatherproof Connections:** IP65/67 connectors suitable for outdoor festival use.

## 2. Should Have
*   **ESP32 Core:** Use of an ESP32 microcontroller for primary logic and timing.
*   **Fail-Safe Biasing:** Hardware biasing to ensure the DMX bus stays in a known state if the signal is lost.
*   **Isolation:** 5kV Galvanic Isolation between DMX bus and logic.
*   **Protection:** TVS Diode arrays on all data lines.
*   **Stability:** Active fail-safe biasing to prevent flickering on floating data lines.
*   **JLC-Optimized BOM:** Design utilizing "Basic" parts from the JLCPCB library to meet a £15-20 per unit (in batches of 25x) target.
*   **Enclosure:** Make use of the original beacons parts as much as possible.
*   **Thermal:** Designed for passive cooling at 100% duty cycle across all channels.

## 3. Could Have
*   **Art-Net Support:** Connectivity via RJ45 (Ethernet) to allow for modern lighting network integration.
*   **OTA Updates:** Ability to update firmware over Wi-Fi for last-minute festival bug fixes.
*   **On-board Thermal Monitoring:** Using the ESP32 internal sensor or a dedicated NTC to monitor the PCBA temperature during high-intensity strobe sequences.
*   **Enclosure:** Replace parts of the beacon with custom parts to aid assembly and robustness.
*   **Web Configuration Portal:** An ESP32-hosted captive portal to set DMX start addresses or Art-Net universes without reflashing.
*   **RDM Support:** Remote Device Management over the DMX line for remote addressing.


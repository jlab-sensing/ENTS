# Diagnostics and LEDs

This guide explains how to interpret the onboard status LEDs, inspect boot diagnostic messages over the USB serial terminal, and perform hardware resets.

---

## 1. Status LED Codes

The primary diagnostic indicator is the status LED located near the white `RST` button at the corner of the ENTS board:

| LED Pattern | Operating State | Expected Action |
| :--- | :--- | :--- |
| **Slow Blink** (~1 Hz) | Searching for network connection (WiFi SSID scan or LoRaWAN join request). | Wait for connection. If persistent, check gateway coverage or WiFi credentials. |
| **Fast Blink** (~4 Hz) | Connecting to ingestion endpoint and transmitting telemetry packets. | Normal transmission state. |
| **LED Turns Off** | Packet successfully uploaded; microcontroller entering low-power sleep mode. | Normal operating cycle. The LED will remain off until the next sampling interval. |
| **Solid ON** | Unrecoverable error encountered; firmware execution halted. | Perform a hardware reset and inspect serial logs. |

---

## 2. Hardware Reset Procedures

The ENTS board includes two tactile switches: a white `RST` button near the USB-C corner, and a blue button.

### Soft Reboot
* Press and release the white **RST** button.
* Reinitializes the microcontroller and restarts the configured sensing loop.

### Full Power-Cycle Reset
If the status LED remains solid or the board becomes unresponsive:
1. Connect the board to power.
2. Press and hold both the **Blue** button and **White** `RST` button simultaneously.
3. Release the **Blue** button first.
4. Release the **White** `RST` button second.
5. The board will perform a full hardware reboot.

---

## 3. Serial Monitor Diagnostics

Connecting the ENTS board to a computer over USB allows you to inspect bootloader telemetry, firmware commit hashes, and device EUIs.

### Prerequisites

* **USB-to-UART Driver**: The ENTS board uses a Silicon Labs CP2102 USB bridge. Most modern Linux and macOS kernels support this natively; Windows users can download drivers from [Silicon Labs](https://www.silabs.com/software-and-tools/usb-to-uart-bridge-vcp-drivers).
* **Terminal Software**: Standard serial terminal programs include:
  * Linux / macOS: `screen`, `minicom`, or `tio`
  * Windows: PuTTY, Tera Term, or CoolTerm
  * Android: Serial USB Terminal (over USB OTG)

### Connection Parameters

* **Baud Rate**: `115200`
* **Data Bits**: `8`
* **Parity**: `None`
* **Stop Bits**: `1` (8N1)
* **Flow Control**: `None`

### Inspecting the Boot Banner

1. Open your serial terminal program on the detected port (for example, `/dev/ttyUSB0` on Linux or `COM3` on Windows).
2. Press the white **RST** button on the ENTS board.
3. The board will print its startup banner:

```text
==================================================
  _____ _   _ _____ ____  
 | ____| \ | |_   _/ ___| 
 |  _| |  \| | | | \___ \ 
 | |___| |\  | | |  ___) |
 |_____|_| \_| |_| |____/ 
 
 Environmental NeTworked Sensing (ENTS) Node
 Firmware Commit: 3031db9 (2026-01-08)
 DevEUI:  0080E1150006099A
 JoinEUI: 0000000000000000
 AppKey:  2B7E151628AED2A6ABF7158809CF4F3C
==================================================
[INFO] Battery Voltage: 4.12 V
[INFO] Initializing SDI-12 bus... OK
[INFO] Initializing I2C bus... OK
[INFO] Reading analog sensors... OK
```

### Verifying Firmware Version

* Locate the `Firmware Commit` string in the boot output.
* Compare this commit hash against the latest release tag in the [ENTS-node-firmware releases page](https://github.com/jlab-sensing/soil-power-sensor-firmware/releases).
* If your board is running older firmware, refer to the developer instructions for flashing updated binaries over SWD or UART.

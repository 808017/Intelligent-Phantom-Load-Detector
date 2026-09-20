# ⚡ Intelligent Phantom Load Detector

### IoT-Based Real-Time Detection and Monitoring of Standby Power Consumption

![ESP32](https://img.shields.io/badge/Platform-ESP32-blue)
![ESP-NOW](https://img.shields.io/badge/Wireless-ESP--NOW-green)
![MQTT](https://img.shields.io/badge/Cloud-MQTT-orange)
![Status](https://img.shields.io/badge/Status-Working%20Prototype-success)

---

## 📷 Working Prototype

![Working Prototype](images/prototype/working-prototype.jpg)

---

## Overview

The Intelligent Phantom Load Detector is an IoT-based
energy monitoring prototype designed to identify standby
or phantom energy consumption from connected appliances.

The system consists of two ESP32-based units:

1. Sensor Unit
2. Receiver and Processing Unit

The sensor unit measures AC voltage and current and
transmits the measurement data wirelessly using ESP-NOW.

The receiver processes the received data, displays
measurements locally and publishes data to an MQTT-based
cloud dashboard.

---

## Key Features

- Non-invasive current measurement
- AC voltage measurement
- Real-time power monitoring
- ESP-NOW wireless communication
- MQTT cloud connectivity
- Phantom-load detection
- Energy consumption monitoring
- 20x4 LCD interface
- Audible alerts
- Configurable measurement thresholds
- Measurement statistics
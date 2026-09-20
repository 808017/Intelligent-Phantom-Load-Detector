# ⚡ Intelligent Phantom Load Detector

### IoT-Based Real-Time Detection and Monitoring of Standby Power Consumption

![ESP32](https://img.shields.io/badge/Platform-ESP32-blue)
![ESP--NOW](https://img.shields.io/badge/Wireless-ESP--NOW-green)
![MQTT](https://img.shields.io/badge/Cloud-MQTT-orange)
![Arduino](https://img.shields.io/badge/Firmware-Arduino%20IDE-00979D)
![ADS1115](https://img.shields.io/badge/ADC-ADS1115-red)
![Status](https://img.shields.io/badge/Status-Working%20Prototype-success)

---

## 📷 Working Prototype

![Working Prototype](images/prototype/working-prototype.jpg)

> A distributed IoT-based prototype for monitoring electrical parameters
> and identifying potential standby/phantom-load conditions.

---

# 📌 Project Overview

The **Intelligent Phantom Load Detector** is an IoT-based energy monitoring
system designed to detect and monitor **standby or phantom energy
consumption** from electrical appliances.

Many electrical and electronic appliances continue to consume a small
amount of electricity even when they appear to be switched off or are
operating in standby mode. This hidden consumption can accumulate over
long periods and contribute to unnecessary energy usage.

This project addresses the problem using a distributed sensing and
processing architecture.

The system consists of two main units:

- **Sensor Unit**
- **Receiver and Processing Unit**

The Sensor Unit measures AC voltage and current using dedicated sensing
circuits and an external ADC. The measured data is transmitted wirelessly
to the Receiver Unit using **ESP-NOW**.

The Receiver Unit processes the received measurements, calculates
electrical parameters and energy consumption, displays information on a
20×4 LCD, generates audible alerts and publishes selected data to an
MQTT-based cloud platform.

---

# 🎯 Project Objectives

The main objectives of the project are:

- Develop a non-invasive system for measuring AC electrical parameters.
- Measure real-time AC voltage and current.
- Calculate power and related electrical parameters.
- Identify potential standby/phantom-load conditions.
- Transfer measurement data wirelessly between sensor and receiver units.
- Provide real-time local monitoring through an LCD.
- Provide audible alerts for configured abnormal conditions.
- Send measurement data to an IoT cloud platform.
- Monitor energy consumption over time.
- Provide configurable measurement thresholds and system statistics.

---

# 💡 Problem Statement

Modern electrical appliances often remain connected to the mains even
when they are not actively being used.

Devices such as:

- Televisions
- Set-top boxes
- Chargers
- Computers
- Monitors
- Gaming consoles
- Audio systems
- Smart appliances

may continue to consume electricity in standby or low-power states.

This project aims to provide a practical method of monitoring such
consumption and notifying the user when a configured phantom-load
condition is detected.

---

# 🧠 System Concept

The system follows the architecture:

```text
                ELECTRICAL APPLIANCE
                       │
                       │
             ┌─────────┴─────────┐
             │                   │
          AC Voltage          AC Current
             │                   │
             ▼                   ▼
        ZMPT101B             SCT-013-000
             │                   │
             └─────────┬─────────┘
                       │
                       ▼
                  ADS1115 ADC
                       │
                       ▼
                ┌──────────────┐
                │ SENSOR UNIT  │
                │    ESP32     │
                └──────┬───────┘
                       │
                    ESP-NOW
                       │
                       ▼
              ┌──────────────────┐
              │ RECEIVER UNIT    │
              │      ESP32       │
              │                  │
              │  20×4 LCD        │
              │  Buzzer          │
              │  Processing      │
              └────────┬─────────┘
                       │
                      Wi-Fi
                       │
                       ▼
                ┌──────────────┐
                │ MQTT / Cloud │
                │  Dashboard   │
                └──────────────┘

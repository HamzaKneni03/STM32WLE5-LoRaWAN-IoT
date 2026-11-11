# STM32WLE5 LoRaWAN IoT Monitoring Project

An embedded IoT project exploring long-range wireless communication using the **STM32WLE5 (Wio-E5 Development Kit)**, LoRaWAN technology, and **The Things Network (TTN)**.

Developed during my engineering internship at **YUCCAINFO**, this project focuses on understanding, configuring, and testing a LoRaWAN-based IoT communication system.

---

## Project Overview

The project aims to develop and experiment with an embedded wireless monitoring system based on LoRaWAN.

The Wio-E5 Development Kit, powered by the STM32WLE5JC microcontroller, is used as the end-device platform. It communicates wirelessly with a LoRaWAN gateway, which forwards data to The Things Network (TTN).

The project covers hardware exploration, AT command configuration, wireless communication, gateway integration, and IoT network fundamentals.

## Project Objectives

- Explore the STM32WLE5-based Wio-E5 Development Kit.
- Understand LoRa and LoRaWAN communication principles.
- Configure the LoRa-E5 module using AT commands.
- Establish communication with The Things Network (TTN).
- Understand the role of a LoRaWAN gateway in an IoT network.
- Study data transmission and network integration using MQTT.

## System Architecture

The overall communication architecture is based on the following components:

```text
+---------------------------+
|     Wio-E5 Development    |
|     Kit (STM32WLE5JC)     |
|                           |
|     LoRaWAN End Device    |
+-------------+-------------+
              |
              | LoRa / LoRaWAN
              |
              v
+---------------------------+
|     Dragino LPS8N         |
|     LoRaWAN Gateway       |
+-------------+-------------+
              |
              | Internet
              |
              v
+---------------------------+
|   The Things Network      |
|          (TTN)            |
|                           |
|   Network Server          |
+-------------+-------------+
              |
              | MQTT / Data Integration
              |
              v
+---------------------------+
|     IoT Application       |
|   (Future Integration)   |
+---------------------------+
```

## Hardware Components

| Component | Description |
|---|---|
| Wio-E5 Development Kit | LoRaWAN end-device development board |
| STM32WLE5JC | ARM Cortex-M4 microcontroller with integrated LoRa radio |
| Dragino LPS8N | LoRaWAN gateway |
| LoRa Antenna | Wireless signal transmission and reception |
| USB Interface | Power supply and serial communication |

## Technologies and Tools

- **Embedded Systems:** STM32WLE5JC
- **Wireless Communication:** LoRa / LoRaWAN
- **Module Configuration:** AT Commands
- **IoT Network Server:** The Things Network (TTN)
- **Gateway:** Dragino LPS8N
- **Data Integration:** MQTT (integration and exploration)
- **Hardware Documentation:** Development board and pinout analysis

## Repository Structure

```text
STM32WLE5-LoRaWAN-IoT/
│
├── Documentation/       # Project documentation
│
├── Firmware/            # Embedded firmware
│
├── Gateway/             # Gateway configuration and integration
│
├── Hardware/
│   ├── Schematics/      # Hardware schematics
│   └── Wio-E5/
│       ├── Images/      # Board, peripherals and pinout images
│       └── README.md    # Wio-E5 technical documentation
│
├── LoRaWAN/             # LoRaWAN configuration and concepts
│
├── Tests/               # Communication tests and results
│
└── README.md            # Main project documentation
```

## Project Workflow

1. Study the Wio-E5 Development Kit and its hardware interfaces.
2. Explore the STM32WLE5JC microcontroller and its peripherals.
3. Configure the LoRa-E5 module using AT commands.
4. Connect the end device to The Things Network.
5. Configure and test communication through the Dragino LPS8N gateway.
6. Study data reception and IoT data integration.

## Current Progress

- [x] Wio-E5 Development Kit hardware exploration.
- [x] Board peripherals and pinout documentation.
- [x] LoRa-E5 AT command configuration.
- [x] Initial LoRaWAN communication experiments with TTN.
- [x] Dragino LPS8N gateway integration and testing.
- [ ] Complete firmware documentation.
- [ ] Organize communication test results.
- [ ] Extend MQTT-based data integration.

## Author

**Hamza Kneni**

Engineering Student – Electronics and Embedded Systems

- GitHub: [@HamzaKneni03](https://github.com/HamzaKneni03)

---

*This repository documents the technical exploration, implementation steps, and experiments carried out throughout the project.*

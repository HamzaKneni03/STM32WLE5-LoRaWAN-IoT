# RAK3172 – Electronic Design

## 1. Overview

This section presents the electronic design of a custom board based on the RAK3172 module, which integrates the STM32WLE5 microcontroller and LoRa transceiver.

The design is divided into six main functional blocks:

- USB-C and UART communication interface
- LiPo battery charger
- Battery voltage monitoring
- Power regulation and management
- SWD debugging and programming interface
- Main RAK3172 system

## 2. Complete Schematic

The complete electrical schematic designed using Altium Designer is available below.

[**View the complete RAK3172 schematic (PDF)**](RAK3172_Schematic.pdf)

## 3. Functional Block Analysis

### 3.1. USB-C and UART Bridge

**Purpose**

This block allows a computer to communicate with the RAK3172 module through a USB-C connection and a UART interface connected to PA9 and PA10.

It supports:
- Debugging and serial communication.
- Sending AT commands.
- Communication between the PC and the RAK3172 module.

**Main components**

| Component | Reference / Value | Function |
|---|---|---|
| USB-C connector | J3 | Connects the board to a computer |
| CH340E | U2 | USB-to-UART converter |
| Resistors | R3, R4 – 5.1 kΩ | CC1 and CC2 pull-down resistors |
| Capacitor | C7 – 100 nF | Power supply decoupling |
| Test points | TP2, TP3 | USB signal testing |
| Jumpers | JP3, JP5, JP6 | Enable or disable UART and power signals |
| UART signals | TXD, RXD | Connect to PA9 and PA10 of the RAK3172 |

### 3.2. LiPo Battery Charger

**Purpose**

This block charges a single-cell LiPo battery (3.7 V nominal) directly from the USB-C power supply.

It uses the MCP73831 dedicated Li-Ion/LiPo charging controller.

**Main components**

| Component | Reference / Value | Function |
|---|---|---|
| Charging controller | U3 – MCP73831T-2ACI/OT | LiPo battery charging management |
| Programming resistor | R5 – 5.1 kΩ (value to verify) | Sets the charging current |
| LED | D2 – Red | Indicates charging status through STAT |
| Resistor | R6 – 1 kΩ | Limits LED current |
| Capacitor | C8 – 10 µF | Filters the battery supply |
| Battery connector | J6 – JST-2PH | Connects the LiPo battery |

### 3.3. Battery Voltage Monitoring

**Purpose**

This block measures the battery voltage using the PA4 analog input of the STM32 ADC.

A voltage divider is used because the battery voltage can reach approximately 4 V.

**Main components**

| Component | Reference / Value | Function |
|---|---|---|
| Resistor | R9 – Value to be confirmed | First resistor of the voltage divider |
| Resistor | R10 – 10 MΩ | Second resistor of the voltage divider |
| Solder jumpers | JP1, JP4 | Enable or disable battery monitoring |
| Capacitor | C11 – 100 nF | Filters noise from the measured signal |
| Analog input | PA4 | Reads the divided battery voltage |

### 3.4. Power Regulation and Management

**Purpose**

This block provides a stable 3.3 V supply for the RAK3172 module and the other electronic components.

The design uses a USB/battery power selection circuit, with USB-C given priority, followed by 3.3 V regulation.

**Main components**

| Component | Reference / Value | Function |
|---|---|---|
| LDO regulator | U4 – XC6202B331MR-G | Regulates the supply to 3.3 V |
| P-channel MOSFET | Q1 – DMG3415U-7 | Automatic USB/battery power selection |
| Resistors | R7, R8 – 10 kΩ | Control the MOSFET |
| Schottky diode | D3 – B5819W | Protects against VBUS reverse current |
| Capacitors | C9, C10 – 10 µF | Input and output filtering |

### 3.5. SWD Debugging and Programming

**Purpose**

The Serial Wire Debug (SWD) interface allows external programming and real-time debugging of the RAK3172 module.

An external ST-Link programmer can be connected using wires or a dedicated soldered SWD connector.

### 3.6. Main RAK3172 System

**Purpose**

The main block is based on the RAK3172 module, integrating the STM32WLE5 microcontroller and LoRa communication capabilities.

Its main functions include:
- Processing sensor data.
- Executing the embedded application.
- Managing LoRaWAN communication.

**Main components**

| Component | Reference / Value | Function |
|---|---|---|
| RAK3172 module | U1 – STM32WLE5 | Main microcontroller and LoRa communication module |
| Reset button | SW1 | Resets the microcontroller |
| Boot button | SW2 | Enters bootloader mode |
| Resistor | R12 – 1 kΩ | Limits status LED current |
| LED | D1 – Blue | Indicates board status |
| Capacitor | C1 – 100 nF | Decouples the module power supply |

## 4. Design Summary

The electronic design combines communication, battery charging, battery monitoring, power management, debugging, and LoRaWAN processing in a single RAK3172-based system.

The complete schematic is provided in the PDF file for detailed inspection of the electrical connections and component organization.

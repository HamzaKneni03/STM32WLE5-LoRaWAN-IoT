# Hardware Architecture – STM32WLE5JC

## 1. Overview

The hardware architecture of this project is based on the **STM32WLE5JC**, a low-power wireless microcontroller from the STM32WL series developed by STMicroelectronics.

Unlike conventional embedded systems that require an external microcontroller and a separate radio transceiver, the STM32WLE5JC integrates both processing and Sub-GHz wireless communication capabilities into a single chip.

This System-on-Chip (SoC) architecture makes it particularly suitable for long-range, low-power Internet of Things (IoT) applications.

In this project, the STM32WLE5JC is integrated into the LoRa-E5 Development Board, which provides the interfaces required for prototyping and wireless communication experiments.

## 2. STM32WLE5JC Architecture

The STM32WLE5JC combines two main functional blocks:

- **Microcontroller unit (MCU):** Executes embedded applications and manages peripherals.
- **Sub-GHz radio subsystem:** Handles wireless transmission and reception using supported radio modulation schemes.

The main processing core is an Arm Cortex-M4 operating at up to 48 MHz, featuring DSP instructions and a Memory Protection Unit (MPU).

### 2.1. Main Hardware Specifications

| Component | Specification |
|---|---|
| Microcontroller | STM32WLE5JC |
| CPU architecture | 32-bit Arm Cortex-M4 |
| Maximum CPU frequency | 48 MHz |
| Flash memory | Up to 256 KB |
| SRAM | Up to 64 KB |
| Operating voltage | 1.8 V – 3.6 V |
| Operating temperature | -40 °C to +85 °C with radio operation |
| Radio frequency range | 150 MHz – 960 MHz |
| Modulations | LoRa, (G)FSK, (G)MSK and BPSK |
| Maximum RF output power | Up to +22 dBm |
| Debug interface | SWD / JTAG |

*Note: These are STM32WLE5JC device-family specifications. Actual RF performance and available interfaces depend on the hardware design and configuration.*

## 3. Internal Architecture

### 3.1. Arm Cortex-M4 Processing Core

The STM32WLE5JC integrates a 32-bit Arm Cortex-M4 processor running at up to 48 MHz.

Its main functions include:

- Executing the embedded application.
- Managing communication interfaces and peripherals.
- Processing sensor measurements.
- Controlling the wireless communication subsystem through the STM32 software libraries.
- Managing power consumption and operating modes.

The Cortex-M4 also provides DSP instructions and an MPU for improved application processing and memory protection.

### 3.2. Integrated Sub-GHz Radio

One of the main advantages of the STM32WLE5JC is its integrated Sub-GHz radio subsystem.

It supports several modulation techniques:

| Modulation | Description |
|---|---|
| LoRa | Long-range communication with high receiver sensitivity |
| (G)FSK | Frequency-shift keying |
| (G)MSK | Minimum-shift keying |
| BPSK | Binary phase-shift keying |

Main radio characteristics:

| Parameter | Specification |
|---|---|
| Frequency range | 150 MHz – 960 MHz |
| High-power transmitter | Up to +22 dBm |
| Low-power transmitter | Up to +15 dBm |
| Maximum LoRa sensitivity | Up to -148 dBm under specified test conditions |

The radio operates in the Sub-GHz frequency range and supports long-range wireless communication protocols, including LoRaWAN.

The RF front-end and antenna matching network must be considered in the hardware design.

### 3.3. MCU and Radio Communication

The STM32WLE5JC integrates the microcontroller and radio into a single chip.

Unlike a conventional architecture using an external SX126x transceiver connected through SPI, the integrated radio is controlled internally by the STM32WL architecture.

Developers interact with the radio through the appropriate STM32 software libraries and hardware abstraction interfaces.

This integration reduces external component requirements and simplifies the overall hardware architecture.

## 4. Memory Architecture

The STM32WLE5JC provides the memory resources required for embedded applications and wireless communication software.

| Memory | Capacity | Purpose |
|---|---|---|
| Flash | Up to 256 KB | Program code and non-volatile data |
| SRAM | Up to 64 KB | Runtime variables, buffers and stack |
| Backup registers | 20 × 32-bit | Retained application data |

The available memory resources are suitable for embedded firmware, communication management and low-power IoT applications.

## 5. Peripherals and Communication Interfaces

The microcontroller integrates several peripheral controllers for connecting external sensors, modules and electronic devices.

| Peripheral | Quantity | Main Function |
|---|---:|---|
| USART | 2 | Serial communication |
| LPUART | 1 | Low-power serial communication |
| SPI | 2 | Synchronous peripheral communication |
| I2C | 3 | Communication with sensors and peripherals |
| ADC | 1 × 12-bit | Analog signal acquisition |
| DAC | 1 × 12-bit | Analog signal generation |
| Comparators | 2 | Analog signal comparison |
| DMA controllers | 2 | Peripheral and memory data transfers |
| GPIO | Up to 43 | Digital input/output |
| RTC | 1 | Real-time clock and wake-up functions |
| Timers | Multiple | PWM, timing and input capture |

These peripherals allow the development of sensor acquisition systems, wireless monitoring devices and low-power embedded applications.

## 6. Low-Power Operating Modes

The STM32WLE5JC is designed for battery-powered applications and provides several low-power operating modes.

| Mode | Typical Current |
|---|---:|
| Shutdown | 31 nA |
| Standby with RTC | 360 nA |
| Stop 2 with RTC | 1.07 µA |

These values are specified under particular operating conditions by STMicroelectronics. Actual consumption depends on the configuration, enabled peripherals, clock sources and external circuitry.

Low-power modes are particularly important for IoT devices that need to operate for extended periods without replacing their batteries.

## 7. LoRaWAN Software Architecture

The STM32WLE5JC provides the hardware capabilities required for LoRa-based communication. However, LoRaWAN network management is implemented through software.

The STM32CubeWL software ecosystem provides development resources for STM32WL devices, including radio drivers and LoRaWAN middleware.

The LoRaWAN software stack supports network activation procedures such as:

- **OTAA (Over-The-Air Activation):** Devices join the network through a join procedure.
- **ABP (Activation By Personalization):** Devices use predefined session parameters.

LoRaWAN also defines different device classes:

- Class A
- Class B
- Class C

The supported regional parameters depend on the selected LoRaWAN stack configuration and regulatory requirements.

## 8. Role in the Project

The STM32WLE5JC is the central processing and wireless communication component of the LoRaWAN monitoring project.

The hardware investigation focused on understanding:

- The STM32WLE5JC architecture and its integrated radio.
- The LoRa-E5 Development Board peripherals and pinout.
- The available serial communication interface.
- The AT command firmware and module configuration.
- The hardware capabilities required for LoRaWAN communication.

The development board was subsequently used for initial communication experiments with The Things Network (TTN) and the Dragino LPS8N gateway.

## 9. Technical References

- [STMicroelectronics – STM32WLE5JC Product Page](https://www.st.com/en/microcontrollers-microprocessors/stm32wle5jc.html)
- [STM32WLE5/E4xx Official Datasheet (DS13105)](https://www.st.com/resource/en/datasheet/stm32wle5jc.pdf)
- [STM32WL Reference Manual (RM0453)](https://www.st.com/en/microcontrollers-microprocessors/stm32wle5jc.html)
- [STM32CubeWL Software Package](https://www.st.com/en/embedded-software/stm32cubewl.html)

## 10. Related Documentation

- [Wio-E5 Development Board](Wio-E5/README.md)
- [LoRaWAN Architecture](../LoRaWAN/README.md)
- [Gateway Documentation](../Gateway/README.md)

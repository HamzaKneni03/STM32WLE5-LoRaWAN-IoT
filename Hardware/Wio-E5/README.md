
# Wio-E5 Development Kit Documentation

The LoRa-E5 Dev Board is a compact and cost-effective development platform designed for evaluating and prototyping applications based on the LoRa-E5 module, which integrates the STM32WLE5JC microcontroller and Sub-GHz radio transceiver. It is suitable for LoRaWAN, LoRa P2P, and other long-range, low-power IoT applications.

**Figure 1: LoRa-E5 Development Board**

![LoRa-E5 Development Board](../../Images/Hardware/LoRa-E5_Development_Board.png)

## Main Features

The following table summarizes the main technical features of the development board.

| Feature | Description |
|---|---|
| Main Module | LoRa-E5 STM32WLE5JC (integrated MCU and Sub-GHz radio) |
| Microcontroller | Arm Cortex-M4, up to 48 MHz |
| Flash Memory | 256 KB |
| SRAM | 64 KB |
| RF Frequency Band | 868 MHz / 915 MHz, depending on the board version |
| Wireless Communication | LoRaWAN and LoRa P2P |
| USB-C Interface | Power supply and serial communication |
| Connectors | 2.54 mm headers, UART, I2C, SPI, ADC, and GPIO |
| Power Supply | 5 V through USB-C or external supply, according to board specifications |
| Operating Modes | AT commands and native STM32 programming |
| Antenna Connector | SMA connector for an external Sub-GHz antenna |

**Figure 2: Main Peripherals of the Development Board**

![LoRa-E5 Board Peripherals](../../Images/Hardware/LoRa-E5_Peripherals.png)

## LoRa-E5 Dev Board Pinout

The LoRa-E5 Dev Board integrates the LoRa-E5 STM32WLE5JC module, combining a 32-bit STM32 microcontroller with a Sub-GHz LoRa radio modem.

The board provides several interfaces accessible through its side headers:

- **Digital and Analog GPIO:** Used to connect sensors and actuators.
- **Communication Interfaces:** UART, LPUART, USART, I2C, and SPI.
- **Debugging Interface:** SWD pads for STM32 programming and debugging.
- **SMA Connector:** Used to connect an external LoRa antenna.
- **USB-C Port:** Used for board power supply and serial communication.
- **BOOT and RESET Controls:** Used to manage the startup process and enter bootloader mode.

The pinout diagram uses different colors to identify the functions of the available pins:

- **Power:** Power supply pins.
- **GND:** Ground pins.
- **ADC:** Analog input pins.
- **UART / USART / I2C / SPI:** Communication interfaces.
- **SWD:** Programming and debugging pins.

**Figure 3: LoRa-E5 Dev Board Pinout Diagram**

![LoRa-E5 Dev Board Pinout](../../Images/Hardware/LoRa-E5_Pinout.png)

---

**Note:** This documentation describes the features and interfaces available on the development board. It does not imply that every interface was used or tested during the internship.

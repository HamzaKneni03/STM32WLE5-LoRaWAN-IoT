# LoRaWAN Technology Documentation

## 1. Introduction

LoRaWAN (Long Range Wide Area Network) is a communication protocol designed for Low Power Wide Area Networks (LPWAN). It enables wireless communication between battery-powered devices and network infrastructure over long distances while maintaining low energy consumption.

It is important to distinguish between:

- **LoRa:** The physical radio modulation technology used to transmit data over long distances.
- **LoRaWAN:** The communication protocol and network architecture built on top of LoRa.

## 2. LoRaWAN Network Architecture

A typical LoRaWAN network consists of the following components:

| Component | Description |
|---|---|
| End Device | Collects sensor data and transmits it using LoRaWAN. |
| Gateway | Receives radio packets from end devices and forwards them to the network server. |
| Network Server | Manages the network, processes received packets and handles communication with gateways. |
| Application Server | Processes application data received from end devices. |
| IoT Platform | Displays, stores and analyzes the collected information. |

### General communication flow

1. The end device collects data from its sensors.
2. The device transmits the data using LoRa modulation.
3. One or more gateways receive the transmitted packets.
4. The network server processes the packets.
5. The application server receives the application data.
6. An IoT platform can display and process the information.

## 3. Uplink and Downlink Communication

LoRaWAN supports two main communication directions:

- **Uplink:** Communication from an end device to the network.
- **Downlink:** Communication from the network to an end device.

Uplink messages are commonly used to transmit sensor measurements, while downlink messages can be used to send configuration information or control commands.

Messages can also be classified as confirmed or unconfirmed, depending on whether an acknowledgment is required.

## 4. LoRaWAN Device Classes

LoRaWAN defines three device classes according to their communication behavior and energy consumption.

### Class A
- Supported by all LoRaWAN devices.
- The device opens two short reception windows after each uplink transmission.
- Provides low power consumption.

### Class B
- Uses scheduled reception windows.
- Receives additional downlink opportunities through synchronized beacon signals.
- Offers more predictable communication availability.

### Class C
- Keeps its reception window open almost continuously.
- Provides low downlink latency.
- Requires more energy than Class A and Class B.

## 5. Activation Methods

A LoRaWAN device must be activated before exchanging application data with the network.

### Over-The-Air Activation (OTAA)

OTAA is an activation procedure in which the device joins the network through a join request and join accept exchange.

It uses device credentials and establishes session keys for subsequent communication.

### Activation By Personalization (ABP)

ABP is an activation method in which the device is configured directly with its network session parameters and keys.

Unlike OTAA, it does not require a join procedure each time the device is activated.

## 6. Security

LoRaWAN includes security mechanisms to protect communication between end devices and the network.

These mechanisms include:
- Device authentication.
- Session key management.
- Encryption of application data.
- Integrity verification of messages.

Network credentials and encryption keys must be kept confidential and must never be published in a public repository.

## 7. Applications

LoRaWAN is suitable for IoT applications requiring long-range communication and low energy consumption, such as:

- Smart agriculture.
- Industrial monitoring.
- Smart metering.
- Environmental monitoring.
- Smart city applications.

## 8. References

- LoRaWAN technical documentation and study notes provided in the project research PDF.
- LoRa Alliance technical resources: https://lora-alliance.org/



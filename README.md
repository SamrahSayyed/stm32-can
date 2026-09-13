# STM32 Sensor-to-ECU Communication over CAN

> Real-time embedded communication framework for integrating sensors with an Electronic Control Unit (ECU) using STM32 and the Controller Area Network (CAN) protocol.

---

## 🚗 Project Overview

This project is a foundational project for **sensor-to-ECU communication framework using STM32 microcontrollers and CAN communication** for automotive embedded applications.

The system is designed to acquire sensor information, process it on an embedded microcontroller, and transmit the resulting data reliably to an ECU over a CAN-based communication network.

The project focuses on the practical challenges involved in building a **real-time, distributed automotive embedded communication system**, including sensor integration, CAN communication, data transmission, testing, debugging, and validation.

---

## 🎯 Problem Statement

Modern vehicles rely on distributed electronic control systems in which sensors and ECUs continuously exchange information.

A reliable communication mechanism is therefore required to:

* Transfer sensor information with predictable timing
* Maintain reliable communication between distributed nodes
* Support multiple automotive electronic subsystems
* Handle sensor and communication data efficiently
* Enable scalable embedded architectures

The objective of this project is to develop and validate a **STM32-based sensor-to-ECU communication framework using CAN** for real-time automotive applications.

---

## 🧠 System Architecture

```text id="z7g4r2"
                 ┌─────────────────┐
                 │     Sensors     │
                 │                 │
                 │  NTC / Hall /   │
                 │   Vibration     │
                 └────────┬────────┘
                          │
                          │ Sensor Data
                          ▼
                 ┌─────────────────┐
                 │      STM32      │
                 │   Sensor Node   │
                 │                 │
                 │ Sensor Reading  │
                 │ Data Processing │
                 └────────┬────────┘
                          │
                          │ CAN Frames
                          ▼
                 ╔═════════════════╗
                 ║    CAN BUS      ║
                 ║                 ║
                 ║ Reliable Data   ║
                 ║ Communication   ║
                 ╚════════╤════════╝
                          │
                          ▼
                 ┌─────────────────┐
                 │      STM32      │
                 │    ECU Node     │
                 │                 │
                 │ CAN Reception   │
                 │ Data Processing │
                 └────────┬────────┘
                          │
                          ▼
                 ┌─────────────────┐
                 │ ECU Application │
                 │ / Monitoring    │
                 └─────────────────┘
```

---

## 🔧 Hardware

| Component         | Purpose                          |
| ----------------- | -------------------------------- |
| STM32L432KC       | Embedded processing / controller |
| TJA1050           | CAN transceiver                  |
| NTC Thermistor    | Temperature sensing              |
| A3144 Hall Sensor | Magnetic / rotational sensing    |
| SW-420            | Vibration detection              |
| 0.96" OLED        | Local data display               |
| CAN Bus           | Inter-node communication         |

---

## 💻 Software & Tools

| Technology / Tool | Purpose                                           |
| ----------------- | ------------------------------------------------- |
| Embedded C        | Firmware development                              |
| STM32CubeIDE      | STM32 development and debugging                   |
| STM32 HAL         | Hardware abstraction and peripheral configuration |
| CAN               | Automotive communication                          |
| DSO               | CAN signal observation and validation             |
| RealTerm          | Serial monitoring / data logging                  |
| Git / GitHub      | Version control                                   |

---

## ⚙️ How the System Works

### 1. Sensor Acquisition

The STM32 sensor node acquires information from the connected sensors.

The implemented sensing setup includes:

* Temperature sensing using an NTC thermistor
* Hall-effect sensing using an A3144 sensor
* Vibration detection using an SW-420 sensor

---

### 2. Embedded Processing

The STM32 processes the sensor readings and prepares the relevant information for transmission.

The embedded firmware is responsible for:

* Sensor interfacing
* Data acquisition
* Data processing
* CAN communication
* ECU-side data reception

---

### 3. CAN Transmission

Processed sensor information is transmitted through the CAN interface.

```text id="c6m5e8"
Sensor Data
     │
     ▼
STM32 Sensor Node
     │
     ▼
CAN Frame
     │
     ▼
CAN Transceiver
     │
     ▼
CAN Bus
     │
     ▼
ECU Node
```

---

### 4. ECU Reception

The receiving STM32 node acts as the ECU-side controller.

It receives the CAN data and processes the incoming information for further monitoring or application-level functionality.

---

### 5. Monitoring & Validation

System behaviour is monitored using development and debugging tools.

CAN signals can be observed using a **digital storage oscilloscope**, while serial communication and logged data can be monitored using **RealTerm**.

---

## 📡 CAN Communication

CAN was selected because it is widely used for communication between distributed electronic systems in automotive environments.

The project demonstrates the complete communication path:

```text id="z2j9n1"
Sensor
  ↓
Sensor Interface
  ↓
STM32
  ↓
CAN Transmission
  ↓
CAN Bus
  ↓
CAN Reception
  ↓
ECU
  ↓
Data Monitoring
```

The communication framework is designed around the requirements of **real-time and reliable exchange of sensor information between embedded nodes**.

---

## 🧪 Testing & Validation

Testing was performed across multiple stages of the system.

### Sensor Testing

Individual sensors were tested to verify that the STM32 could correctly acquire their outputs.

### Firmware Testing

Embedded firmware was tested during sensor acquisition and communication development.

### CAN Testing

CAN communication was monitored to verify transmission and reception between the embedded nodes.

### Signal Validation

A digital storage oscilloscope was used to observe CAN bus signals and validate communication behaviour.

### Debugging

RealTerm and development tools were used for monitoring, logging, and troubleshooting during experimentation.

---

## 🛡️ Reliability Considerations

Automotive communication systems must continue to provide dependable information exchange despite being distributed across multiple electronic nodes.

The project therefore focuses on:

* Reliable sensor data transmission
* Structured CAN-based communication
* Real-time data exchange
* Communication validation
* Fault-aware system testing
* Scalable distributed architecture

These considerations form the basis for extending the system toward more complex automotive applications.

---

## 🏎️ Automotive Applications

The developed communication architecture can serve as a foundation for applications involving:

* Sensor-to-ECU communication
* Vehicle monitoring systems
* Distributed automotive ECUs
* Automotive diagnostics
* ADAS subsystems
* Real-time vehicle sensing
* Embedded vehicle control systems

---

## 🔬 Research Contribution

The work associated with this project was developed into a research publication on **multi-sensor integration using STM32 over a CAN-based communication framework**.

### Publication

**"Design and Implementation of Multi-Sensor Integration using STM32 over CAN-Based Communication Framework"**

Published in **IEEE Xplore, 2026**.

The research investigates the design and implementation of a CAN-based embedded framework for integrating multiple sensors with STM32-based automotive communication systems.

---

## 📊 Project Pipeline

```text id="q4f8r6"
┌──────────────┐
│    Sensors   │
└──────┬───────┘
       │
       ▼
┌──────────────┐
│ Sensor       │
│ Acquisition  │
└──────┬───────┘
       │
       ▼
┌──────────────┐
│ STM32 Sensor │
│ Node         │
└──────┬───────┘
       │
       ▼
┌──────────────┐
│ CAN Frame    │
│ Generation   │
└──────┬───────┘
       │
       ▼
════════════════════
       CAN BUS
════════════════════
       │
       ▼
┌──────────────┐
│ CAN Frame    │
│ Reception    │
└──────┬───────┘
       │
       ▼
┌──────────────┐
│ STM32 ECU    │
│ Node         │
└──────┬───────┘
       │
       ▼
┌──────────────┐
│ Data         │
│ Monitoring   │
└──────────────┘
```

---

## 🔮 Future Improvements

Potential extensions include:

* Integrating an actual ECU with different sensors
* Additional automotive sensors
* Advanced CAN message handling
* CAN diagnostics
* Fault detection and reporting
* CANoe/CANalyzer-based validation
* Integration with higher-level ECU applications
* Automotive network scalability testing
* Integration with ADAS perception systems
* Reliability-aware driver feedback mechanisms

---

## 🧰 Skills Demonstrated

This project demonstrates hands-on experience with:

* STM32 microcontrollers
* Embedded C
* Sensor interfacing
* CAN protocol
* CAN transceivers
* Real-time embedded communication
* ECU architecture
* Hardware/software integration
* Embedded debugging
* CAN signal validation
* System testing
* Automotive embedded systems
* Distributed electronic systems

---

## 👩‍💻 Author

**Samrah Sayyed**

Electrical & Computer Engineering Undergraduate
MIT World Peace University

Areas of interest:

**Automotive Embedded Systems • ADAS • CAN Communication • Sensor Integration • Real-Time Embedded Systems**

GitHub: https://github.com/SamrahSayyed

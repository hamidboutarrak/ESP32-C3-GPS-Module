# ESP32-C3 GPS Module

An open-source hardware project featuring an ESP32-C3 microcontroller integrated with a NEO-M9N GPS module, designed for location-based IoT applications.

![Project Status](https://github.com/hamidboutarrak/ESP32-C3-GPS-Module/blob/main/Images/Screenshot%202025-10-06%20000836.png?raw=true)
![Hardware]([https://img.shields.io/badge/hardware-ESP32--C3-blue.svg](https://github.com/hamidboutarrak/ESP32-C3-GPS-Module/blob/main/Images/Screenshot%202025-10-06%20000853.png?raw=true))
![License](https://img.shields.io/badge/license-MIT-green.svg)

## 📋 Overview

This project provides a complete hardware design for an ESP32-C3 based GPS module with USB connectivity. The board combines the power of ESP32-C3's WiFi/BLE capabilities with precise GPS positioning from the u-blox NEO-M9N module, making it ideal for tracking, navigation, and location-aware IoT applications.

## ✨ Features

- **ESP32-C3-MINI** microcontroller with WiFi and BLE 5.0
- **NEO-M9N GPS module** with high accuracy positioning
- **USB-to-UART bridge** (integrated USB interface)
- **Micro USB-B connector** for power and programming
- **5V to 3.3V voltage regulation**
- **External antenna connector** with FL1 connector
- **Reset and Boot buttons** for easy programming
- **Power and User LEDs** for status indication
- **Compact design** optimized for integration

## 🔧 Hardware Specifications

### Main Components

| Component | Description | Part Number |
|-----------|-------------|-------------|
| Microcontroller | ESP32-C3-MINI | ESP32-C3-MINI-1 |
| GPS Module | u-blox NEO-M9N | NEO-M9N |
| USB-to-UART | USB to Serial Bridge | U2 |
| Voltage Regulator | 5V to 3.3V LDO | U3 |
| USB Connector | Micro USB-B | J3 |
| Antenna Connector | FL1 Type | J4 |

### Pin Mapping

#### ESP32-C3 GPIO Connections
- **GPIO0**: Boot control / User defined
- **GPIO1-GPIO10**: General purpose I/O (available on headers)
- **GPIO18**: USB D- (for USB OTG)
- **GPIO19**: USB D+ (for USB OTG)
- **GPIO20**: U0RXD (UART RX)
- **GPIO21**: U0TXD (UART TX)

#### GPS Module Interface
- TXD/RXD: UART communication with ESP32-C3
- SCL/SDA: I2C interface option
- TIMEPULSE: Time pulse output
- RESET_N: Reset pin
- SAFEBOOT_N: Safe boot mode

### Power Supply
- **Input Voltage**: 5V via USB
- **Operating Voltage**: 3.3V (regulated)
- **USB Interface**: Micro USB-B

## 📁 Repository Structure

```
├── Source/
│   ├── Altium/              # Altium Designer project files
│      ├── *.PrjPcb        # Altium project
│      ├── *.SchDoc        # Schematic documents
│      ├── *.PcbDoc        # PCB documents
│      └── *.LibPkg        # Component libraries
├── Documentation/
│   ├── Assembly_Guide.md    # Assembly instructions
│   └── User_Manual.md       # User guide
├── Images/                  # Photos and renders
└── README.md
```

## 🚀 Getting Started

### Hardware Setup

1. **Power the board** via Micro USB cable
2. **Connect GPS antenna** to the FL1 connector
3. **Install drivers** if required (CP210x or CH340 depending on USB-to-UART chip)

### Programming the ESP32-C3

1. **Enter bootloader mode**: Hold BOOT button, press RESET, release BOOT
2. **Use ESP-IDF or Arduino IDE** to upload firmware
3. **Select board**: ESP32-C3 Dev Module
4. **Select port**: Your USB serial port

### GPS Communication

The NEO-M9N GPS module communicates via UART. Configure your code to read NMEA sentences or use UBX protocol for advanced features.

Example baud rate: **9600** or **38400** (check module configuration)

## 🛠️ Manufacturing

### PCB Specifications
- **Layers**: 2 or 4 layer (specify based on your design)
- **PCB Thickness**: 1.6mm
- **Copper Weight**: 1oz
- **Surface Finish**: ENIG or HASL
- **Minimum Track/Space**: 6/6 mil

### Assembly Notes
- Use proper ESD protection when handling ESP32-C3 module
- GPS antenna placement is critical for performance
- Ensure proper RF grounding for GPS module
- Keep antenna traces as short as possible

## 📦 Bill of Materials

See `Hardware/BOM/` folder for complete bill of materials with part numbers and suppliers.

## 🤝 Contributing

Contributions are welcome! Please feel free to submit pull requests or open issues for:
- Hardware improvements
- Firmware examples
- Documentation updates
- Bug reports

## 👤 Author

**BOUTARRAK HAMID**

## 🙏 Acknowledgments

- Espressif Systems for ESP32-C3
- u-blox for NEO-M9N GPS module
- Open-source hardware community

## 📧 Contact

For questions or suggestions, please open an issue on GitHub.

---

**Note**: This is an open-source hardware project. Feel free to use, modify, and distribute according to the license terms.

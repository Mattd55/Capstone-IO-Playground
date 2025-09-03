# STEM Playground

An interactive IoT educational platform designed to teach integrated systems concepts to grades 6-12 students through hands-on experimentation with sensors, actuators, and real-time web interfaces.

## Overview

The STEM Playground is a complete educational system built around the ESP32 microcontroller that demonstrates how voltage drives integrated systems. Students interact with various sensors and outputs through a custom web interface, learning fundamental engineering concepts in an engaging, hands-on environment.

## Features

- **Real-time Web Interface**: Custom HTML/CSS/JavaScript web application with bidirectional WebSocket communication
- **Multi-Sensor Integration**: Temperature probes, pressure sensors, buttons, switches, and multiple I/O devices
- **Interactive Outputs**: LEDs, servo motors, DC motors with speed control
- **Wireless Connectivity**: ESP32-hosted web server accessible from any device
- **Custom PCB Design**: Professional circuit board for reliable connections and easy assembly
- **Rechargeable Power System**: Lithium-ion battery pack with 27+ hour runtime
- **Educational Resources**: Complete lesson plans and user documentation

## Technologies Used

- **Hardware**: ESP32-WROOM-32, custom PCB, various sensors and actuators
- **Programming**: C++ (Arduino IDE), JavaScript, HTML, CSS
- **Communication**: WebSocket protocol for real-time data transfer
- **Tools**: Arduino IDE, GitHub, Jira, EasyEDA PCB designer
- **Power Management**: Custom voltage regulation with lithium-ion batteries

## System Architecture

[Student Device] <--WiFi--> [ESP32 Microcontroller] <--> [Sensors/Actuators]
|
[Web Server]
|
[Interactive Web Interface]

## Hardware Components

### Inputs
- DS18B20 Temperature Sensor
- Tekscan A301-25 Force/Pressure Sensor  
- Push buttons and switches
- Additional GPIO pins available for expansion

### Outputs
- 6x Multi-colored LEDs (Red, Yellow, Green)
- SG90 Servo Motor (0-180° control)
- DC Motor with speed control
- Expandable to additional actuators

### Power System
- 8x 18650 Lithium-Ion batteries (2S4P configuration)
- Custom voltage regulation (5V output)
- Pololu buck-boost converter
- 27+ hour operational runtime

## Software Features

### Web Interface
- Homepage with system overview
- Individual sensor pages with real-time data visualization
- Interactive controls for all outputs
- Voltage/current/resistance displays demonstrating Ohm's law
- Configuration page for advanced users

### Subsystem Integration
- Temperature-controlled DC motor (simulates thermostat)
- Pressure-activated LED array (force visualization)
- Servo position control via web interface
- Real-time data streaming with WebSocket

## Installation & Setup

### Hardware Assembly
1. Assemble the custom PCB with all components
2. Connect ESP32 and all sensors/actuators via header pins
3. Install and connect the battery pack
4. Verify all connections match the provided schematics

### Software Installation
1. Install Arduino IDE
2. Add ESP32 board support via Boards Manager
3. Clone this repository
4. Install required libraries:
   - ArduinoJson
   - AsyncTCP
   - ESPAsyncWebServer
   - DallasTemperature
   - ESP32Servo
   - OneWire
   - WebSockets
   - ezButton

### Programming the Device
1. Open `io_playground.ino` in Arduino IDE
2. Update the static IP address (line 62) for each device
3. Connect ESP32 via USB and upload the code
4. Connect to the OSU_STEM WiFi network (password: 123456789)
5. Navigate to the device's IP address in a web browser

## Usage

### For Educators
- Power on the device and connect students' devices to the provided WiFi network
- Each device displays its IP address and QR code for easy connection
- Follow the included 45-minute lesson plan
- Use the web interface to demonstrate voltage relationships in real-time

### For Students
- Connect to the device's WiFi network
- Navigate to the IP address or scan the QR code
- Explore different sensor pages and observe real-time data
- Experiment with inputs and observe corresponding outputs
- Learn how voltage drives all integrated systems

## Project Structure
```
├── io_playground.ino          # Main ESP32 code (C++)
├── index.h                    # Homepage HTML
├── led.h                      # LED control page
├── temperature.h              # Temperature sensor page
├── pressure.h                 # Pressure sensor page
├── servo.h                    # Servo motor page
├── dcmotor.h                  # DC motor page
├── temp_dcmotor.h            # Temperature-DC motor subsystem
├── pressure_led.h            # Pressure-LED subsystem
├── PCB/                      # PCB design files (EasyEDA)
└── docs/                     # User manual and documentation
```
## System Requirements

- **Power**: 5V, up to 500mA peak current
- **Network**: 2.4GHz WiFi capability
- **Browser**: Any modern web browser with JavaScript support
- **Operating Temperature**: 0°C to 50°C
- **Safety**: Complies with NESC and IEEE guidelines

## Educational Objectives

Students will learn:
- How voltage drives integrated systems
- Sensor-to-voltage conversion principles
- Real-time data acquisition and processing
- Basic programming and web technologies
- Practical applications of Ohm's law
- System integration and troubleshooting

## Contributing

This project was developed as a senior capstone project for The Ohio State University's STEM Outreach program. Contributions, improvements, and adaptations are welcome for educational purposes.

## Team

- **Matthew DiSanto** - Computer Engineering
- **Andrew Grcic** - Computer Engineering
- **Kyle Saul** - Computer Engineering
- **Angelo Dallas** - Electrical Engineering
- **Ellie Rannebarger** - Electrical Engineering

## Mentors & Sponsors

- **Mark Morscher** - STEM Outreach Program Sponsor
- **Alan Gilbert** - Faculty Advisor
- **Jonah Mikesell** - Hardware Mentor
- **Dr. Anderson** - STEM Outreach Program

## License

This project is open source and available for educational use. Please credit the original team when using or adapting this work.

## Support

For technical support, hardware issues, or educational implementation questions, please refer to the detailed user manual in the `docs/` directory or create an issue in this repository.

---

**Note**: This system is designed for educational environments and includes appropriate safety measures for student use. Always follow proper safety protocols when working with electronic components.

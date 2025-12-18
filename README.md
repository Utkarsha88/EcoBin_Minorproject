# ECOBIN – Smart Compost Monitoring Hardware

## Overview
ECOBIN is an embedded IoT system designed to support the Waste2Worth platform by enabling automated monitoring of composting conditions. The system collects environmental and chemical parameters from a compost bin and transmits them wirelessly to the Waste2Worth Flutter application for analysis and visualization.

---

## System Capabilities
- Continuous sensing of compost temperature, humidity, pH value, and gas concentration
- Wireless data transmission using ESP32 WiFi and Bluetooth features
- Local retention of recent sensor readings during network interruptions

---

## Hardware Specification

| Module | Count | Description |
|------|------|-------------|
| ESP32 Development Board | 1 | Controls sensors and manages wireless communication |
| DHT11 Sensor | 1 | Measures ambient temperature and humidity |
| MQ-135 Gas Sensor | 1 | Detects gases such as ammonia and carbon dioxide |
| Analog pH Sensor | 1 | Evaluates acidity level of compost material |

---

## Software Requirements

The firmware development environment is based on the following tools:
- PlatformIO IDE extension for VS Code
- External Libraries:
  - DHT Sensor Library for temperature and humidity acquisition
  - ESP32 Firebase Client for real-time database communication

---

## Installation Procedure

### Step 1: Repository Setup
```bash
git clone https://github.com/Utkarsha88/EcoBin_Minorproject.git
```

### Step 2: Development Environment
- Install Visual Studio Code
- Add the PlatformIO extension
- Open the ECOBIN project directory in VS Code

### Step 3: Network and Cloud Configuration
Modify the following macros in `src/main.cpp`:

```cpp
#define WIFI_SSID "Your_SSID"
#define WIFI_PASS "Your_Password"
#define FIREBASE_HOST "YOUR_FIREBASE_DATABASE_URL"
#define FIREBASE_AUTH "YOUR_FIREBASE_API_KEY"
```

### Step 4: Dependency Management
- Download required libraries as ZIP files
- Extract and place them inside the `lib` folder
- Alternatively, allow PlatformIO to resolve dependencies automatically

### Step 5: Firmware Upload
- Connect the ESP32 board via USB
- Select the correct board and COM port
- Upload the firmware using PlatformIO

---

## Project Directory Structure
```
ECOBIN/
├── lib/               # Third‑party libraries
├── src/
│   └── main.cpp       # Firmware source code
├── test/              # Testing framework
├── platformio.ini     # Build and board configuration
└── README.md
```

---

## Application Integration

### Communication Pipeline
Sensor Units → ESP32 → MQTT Protocol → Firebase Database → Waste2Worth Mobile App

### Data Packet Format
```json
{
  "temperature": 25.6,
  "humidity": 60,
  "ph": 6.8,
  "gas_ppm": 120
}
```

---

## Deployment Notes
- Install all electronics inside a moisture‑resistant enclosure
- Place sensors strategically within the compost bin for accurate readings
- Supported power sources:
  - 18650 rechargeable lithium battery (solar charging compatible)
  - Regulated 5V DC power adapter

---

## Summary
ECOBIN provides a reliable hardware foundation for intelligent compost management. When integrated with the Waste2Worth application, it enables data‑driven insights for sustainable waste handling and compost optimization.


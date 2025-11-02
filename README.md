# AgriGrow 🌾

**A smart soil analysis & crop recommendation platform — IoT + Cloud + AI for sustainable farming**

[![License](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)

## 📖 Table of Contents

- [Overview](#overview)
- [Key Features](#key-features)
- [Architecture](#architecture)
- [Hardware Components](#hardware-components)
- [Software Stack](#software-stack)
- [Installation](#installation)
- [Usage](#usage)
- [Mobile Application](#mobile-application)
- [Machine Learning Integration](#machine-learning-integration)
- [Future Enhancements](#future-enhancements)
- [Contributing](#contributing)
- [License](#license)
- [Acknowledgments](#acknowledgments)

## 🌟 Overview

AgriGrow bridges soil science and digital agriculture by providing real-time soil monitoring and intelligent fertilizer recommendations. It combines low-cost IoT sensors with cloud connectivity and machine learning to deliver crop-specific nutrient dosing, irrigation alerts, and long-term soil health insights.

Key benefits:
- Real-time multi-depth soil monitoring
- AI-driven fertilizer & pesticide recommendations
- Mobile access and remote monitoring
- Reduced fertilizer wastage and improved sustainability

## 🎯 Objectives

- Enable continuous soil data acquisition with low-cost sensors
- Provide AI-based nutrient and fertilizer recommendations
- Integrate with mobile apps for instant access to soil metrics
- Support cloud storage and remote monitoring for scalable deployments
- Reduce fertilizer overuse and protect groundwater

## ✨ Key Features

### 🔬 Smart Soil Analysis
- Monitor N, P, K levels, pH, and moisture at multiple depths
- Optional pesticide/chemical residue detection for toxicity checks
- Local data preprocessing on ESP32 for efficient telemetry

### ☁️ Cloud Connectivity
- Transmit data using ESP32 (Wi‑Fi) via MQTT or HTTPS
- Store time-series data in Firebase / ThingsBoard / AWS IoT
- Multi-location sync and historical trends

### 🤖 AI-Powered Recommendations
- Regression and lightweight RBFN models for nutrient prediction
- Crop-aware fertilizer dosing (growth-stage aware)
- Trend detection and nutrient-deficiency forecasting

### 📱 Mobile App Integration
- Live dashboards for NPK, pH, moisture and trends
- Crop advisory with recommended dosages and alerts
- Device management and notifications for irrigation/nutrients

### 🔋 Hardware Efficiency & Sustainability
- Low power consumption; battery/solar-compatible
- Weatherproof enclosures for field deployment
- Promotes eco-friendly fertilization practices

## 🏗️ Architecture

System overview:

```
     +---------------------------+
     |       Sensor Layer        |
     |---------------------------|
     | NPK | pH | Moisture | Pesticide |
     +---------------+---------------+
                     |
                     v
             +---------------+
             |   ESP32 MCU    |
             | (Data Fusion)  |
             +---------------+
                     |
               Wi-Fi / MQTT
                     |
                     v
           +--------------------+
           |  Cloud Database    |
           +--------------------+
                     |
                     v
          +----------------------+ 
          |  Mobile Application  |
          |  (Visualization &    |
          |   Recommendations)   |
          +----------------------+ 
```

## ⚙️ Hardware Components

| Component | Description |
|---|---|
| ESP32 | Wi‑Fi microcontroller for data fusion & transmission |
| NPK sensor | Measures Nitrogen, Phosphorus, Potassium levels |
| pH sensor | Measures soil acidity/alkalinity |
| Soil moisture sensor | Monitors water content at different depths |
| Pesticide detection module | Optional chemical residue evaluation |
| Power | Rechargeable battery or solar charge system |
| Enclosure | Weatherproof casing for field deployment |

## 💻 Software Stack

| Layer | Technology |
|---|---|
| Microcontroller | C/C++ (Arduino IDE or PlatformIO) |
| Communication | MQTT / HTTP over Wi‑Fi |
| Cloud | Firebase / AWS IoT / ThingsBoard |
| Mobile | React Native + TypeScript (Expo) |
| ML | Python — scikit-learn / TensorFlow Lite for mobile |
| Visualization | Charts & dashboards (mobile + web) |

## 🚀 Installation

### Hardware
1. Connect sensors to the ESP32 following the circuit schematic in docs (NPK analog lines, pH analog, moisture ADC, optional pesticide module).
2. Upload firmware using Arduino IDE or PlatformIO.
3. Configure Wi‑Fi SSID/password and cloud endpoint (MQTT broker or HTTP URL) in the firmware.

### Mobile App (development)

Clone the repository and install dependencies:

```powershell
git clone https://github.com/yourusername/AgriGrow.git
cd AgriGrow
npm install
```

Start the Expo development server:

```powershell
npx expo start
```

Run on device/simulator:
- Android: Press `a` or scan the QR code with Expo Go
- iOS: Press `i` (macOS) or scan QR with Camera app
- Web: Press `w`

## 📱 Usage

### Core Workflows

- Real-time soil monitoring: view live NPK, pH, and moisture readings
- Crop Advisory: get crop-specific fertilizer/pesticide recommendations
- Reports: view historical trends and export CSVs
- Alerts: receive notifications for irrigation and nutrient events

### Interface Overview
- Home: live metrics and device/cloud sync status
- Crop Advisory: recommendations and dosing instructions
- Reports: time-series charts and summaries
- Settings: device setup, cloud credentials, notifications

## 🧠 Machine Learning Integration

- Models: Regression and Radial Basis Function Networks (RBFN) for nutrient prediction and dosing.
- Training: use curated crop datasets and field samples to calibrate models.
- Deployment: convert models to TensorFlow Lite for on-device inference where applicable, or run predictions on the cloud for heavier models.
- Inputs: recent NPK, pH, moisture, crop type, growth stage, weather features.

## 🔮 Future Enhancements

- Drone-based soil imaging and automated sampling
- Blockchain traceability for fertilizer usage and provenance
- Multi-language mobile app and localized advisories
- Integration with government soil data portals and precision agriculture services
- Predictive irrigation scheduling using weather + soil models

## 🤝 Contributing

Contributions are welcome!

1. Fork the repo
2. Create a branch: `git checkout -b feature/your-feature`
3. Implement your changes with TypeScript/C++ style and tests where appropriate
4. Commit and push: `git commit -m "Add feature"` / `git push origin feature/your-feature`
5. Open a Pull Request

Guidelines:
- Follow TypeScript for mobile code; comment microcontroller firmware clearly
- Use clear function names and document hardware pin mappings
- Add unit tests for ML data processing pipelines when possible

## 📄 License

This project is licensed under the MIT License — see the `LICENSE` file for details.

## 🙏 Acknowledgments

- NIT Hamirpur for research collaboration
- Open Source Hardware community for sensor libraries and documentation
- Farmers and agronomists for field data and feedback

---

Built with 💚 by the AgriGrow Team — empowering farmers through data-driven agriculture.
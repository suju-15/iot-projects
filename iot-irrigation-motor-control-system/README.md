# Smart Irrigation Monitoring and Controlling System

An ESP32-based IoT system for real-time monitoring and remote control of irrigation, built on the Arduino IoT Cloud.

## Overview

Unpredictable weather and the need for efficient water management make manual irrigation hard to get right, especially for moisture-sensitive crops. This system monitors soil moisture, temperature and humidity in real time, lets the user control the pump and water flow remotely, and can irrigate automatically when moisture falls to critically low levels.

## Features

- Real-time monitoring of soil moisture, temperature and humidity
- Remote ON/OFF control of the water pump through a relay module
- Remote control of water flow through a servo valve
- Automatic irrigation when soil moisture drops below a threshold
- Live dashboard on both mobile and desktop via the Arduino IoT Cloud
- Simple, low-cost design aimed at small and medium-scale farming

## Hardware

| Component | Notes |
| --- | --- |
| ESP32 | Microcontroller and IoT node |
| DHT11 | Temperature and humidity sensor |
| Soil moisture sensor (resistive) | Probes + LM393 comparator module |
| SG90 servo | Water flow control valve |
| 1-channel relay module | Pump / motor switching |

## Pin mapping

| ESP32 pin | Connected to |
| --- | --- |
| GPIO 4 | DHT11 data |
| GPIO 32 | Soil moisture sensor (analog) |
| GPIO 35 | Relay / motor control |
| GPIO 34 | Servo signal |

## Arduino IoT Cloud variables

| Variable | Type | Permission |
| --- | --- | --- |
| temp_1 | CloudTemperatureSensor | Read |
| humid_1 | int | Read |
| moist_1 | int | Read |
| servo_1 | int | Read / Write |
| m_1 | bool | Read / Write |

## Getting started

1. Open the sketch in the Arduino IDE or the Arduino Cloud editor.
2. Fill in your Wi-Fi SSID, password and device key in `arduino_secrets.h`.
3. Select the ESP32 board and upload the sketch.
4. Open the Arduino Cloud dashboard to monitor readings and control the pump and valve.

> Note: `arduino_secrets.h` is committed as an empty template. Never commit your real Wi-Fi credentials or device key.

## Files

| File | Purpose |
| --- | --- |
| `iot-irrigation-motor-control-system.ino` | Main Arduino sketch |
| `thingProperties.h` | Arduino IoT Cloud generated properties |
| `arduino_secrets.h` | Credentials template (fill in locally) |
| `sketch.json` | Arduino sketch metadata |
| `images/` | Dashboard and hardware screenshots |

## Author

Sujay M. S. — Electronics and Communication Engineering, JNN College of Engineering, Shimoga.

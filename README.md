# PORTABLE-COLORIMETRIC-SYSTEM-FOR-RAPID-MILK-SPOILAGE-DETECTION

## Overview

The **Portable Colorimetric System for Rapid Milk Spoilage Detection** is an Edge AI-based embedded system designed to assess milk freshness in real time using colorimetric sensing technology. The system utilizes an RGB color sensor to analyze the optical characteristics of milk samples and classify their quality as **Fresh**, **Moderate**, or **Spoiled**. Results are displayed instantly on an OLED screen, making the device suitable for dairy farms, milk collection centers, and food quality inspection applications.

The project combines embedded electronics, sensor technology, and machine learning concepts to provide a portable, low-cost, and laboratory-independent solution for milk quality monitoring.

---

## Features

* Real-time milk spoilage detection
* RGB and Clear (C) color analysis using TCS34725 sensor
* OLED-based visual output
* Portable and low-power design
* Edge AI-ready architecture
* Cost-effective alternative to laboratory testing
* Suitable for rural and field environments

---

## Project Structure

```text
├── code/
│   └── code.ino
│
├── colour_sensor/
│   └── colour_sensor.ino
│
├── model creation/
│   ├── dataset files
│   ├── TensorFlow training scripts
│   └── model.h
│
└── README.md
```

### Folder Description

#### `/code`

Contains the primary Arduino application responsible for:

* Reading sensor values
* Processing data
* Classifying milk quality
* Displaying results on the OLED screen

#### `/colour_sensor`

Contains standalone sensor testing and calibration code for the TCS34725 color sensor.

#### `/model creation`

Includes:

* Sample datasets
* TensorFlow/Keras training scripts
* Model conversion files
* Exported TensorFlow Lite model (`model.h`)

---

## Hardware Components

| Component       | Description                   |
| --------------- | ----------------------------- |
| Microcontroller | Arduino Uno / Nano / ESP32    |
| Color Sensor    | Adafruit TCS34725 RGB Sensor  |
| Display         | SSD1306 OLED Display (128×64) |
| Communication   | I2C Interface                 |
| Power Supply    | USB / Battery Powered         |

---

## Software & Libraries

### Embedded Development

* Arduino IDE
* Wire.h
* Adafruit_TCS34725.h
* Adafruit_GFX.h
* Adafruit_SSD1306.h

### Machine Learning

* Python
* Google Colab
* TensorFlow / Keras
* TensorFlow Lite
* NumPy
* Pandas

---

## Working Principle

1. Milk sample is placed in front of the TCS34725 sensor.
2. The sensor captures Red, Green, Blue, and Clear light intensity values.
3. Sensor readings are processed by the microcontroller.
4. The algorithm determines milk quality.
5. Classification results are displayed on the OLED screen.

### Current Classification Logic

```cpp
C > 2200      → SPOILED
C >= 1400     → FRESH
C >= 1000     → MODERATE
```

---

## Current Implementation

The present version uses a rule-based classification approach based on the Clear (C) channel obtained from the TCS34725 sensor.

The system:

* Reads RGB+C values
* Evaluates spoilage conditions
* Displays quality status in real time

Although a TensorFlow Lite model is included in the project files, the current firmware does not yet execute neural network inference.

---

## Future Improvements

### 1. TinyML Integration

Deploy the TensorFlow Lite model directly on the microcontroller to replace threshold-based classification with AI-powered predictions.

### 2. Controlled Sensing Environment

Develop a dark enclosure to eliminate ambient light interference and improve measurement consistency.

### 3. Expanded Dataset

Collect 100–200+ milk samples across multiple spoilage stages to improve model accuracy and robustness.

### 4. ESP32-Based IoT System

Upgrade to ESP32 for:

* Wi-Fi connectivity
* Cloud data logging
* Remote monitoring
* Mobile notifications

### 5. Mobile Dashboard

Integrate platforms such as:

* Blynk
* ThingSpeak
* Firebase

for real-time visualization and analytics.

---

## Applications

* Dairy Farms
* Milk Collection Centers
* Food Processing Industries
* Quality Inspection Laboratories
* Cold Storage Facilities
* Dairy Supply Chains

---

## Future Scope

This project can evolve into a complete AI-powered dairy quality monitoring platform capable of:

* Milk spoilage prediction
* Adulteration detection
* Shelf-life estimation
* Cloud-based analytics
* Smart dairy supply chain monitoring

---

## License

This project is developed for educational, research, and innovation purposes. Contributions and improvements are welcome.

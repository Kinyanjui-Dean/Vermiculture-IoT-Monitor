# Vermiculture Bed IoT Monitoring System (Group 3A)

ESP32-based IoT telemetry node and responsive farmer dashboard for monitoring vermiculture beds (soil moisture, air temperature, relative humidity, and simulated pH).

## Hardware Pinout (NodeMCU ESP-32S)
- **DHT22 (Temp/Humidity):** DATA -> GPIO 4, VCC -> 3V3, GND -> GND
- **Capacitive Soil Sensor v1.2:** AOUT -> GPIO 32 (ADC1), VCC -> 3V3, GND -> GND
- **Potentiometer 1 (Simulated pH):** Wiper -> GPIO 34 (ADC1)
- **Potentiometer 2 (Dry Threshold):** Wiper -> GPIO 35 (ADC1)

## Firmware Setup
1. Copy `secrets.h.example` to `firmware/secrets.h` and enter your Wi-Fi credentials and ThingSpeak Write API key.
2. Set a unique `BED_ID` in `firmware/vermiculture_node.ino`.
3. Install the `DHT sensor library` by Adafruit in Arduino IDE and flash to an ESP32 board at `115200` baud.

## Dashboard Usage
Open `dashboard/index.html` in any browser (or via GitHub Pages). It polls ThingSpeak Channel `3584721` every 30 seconds, renders live trend charts, displays plain-language watering/temperature alerts, and exports bed telemetry as CSV.

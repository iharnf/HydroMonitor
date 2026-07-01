# Wiring

## v0.1.0

| Signal | PH-4502C | M5StickC Plus2 |
| --- | --- | --- |
| Power | VCC | 5V |
| Ground | GND | GND |
| Analog pH output | Po | GPIO36 |
| Digital threshold output | Do | NC |
| Temperature output | To | NC |

Before connecting `Po` to the ESP32, measure voltage between `Po` and `GND`.
The current hardware measured 2.7 V, which is below the ESP32 3.3 V input limit.

## Planned DS18B20

This part is not enabled in firmware yet.

| DS18B20 | M5StickC Plus2 |
| --- | --- |
| Red | 5V |
| Black | GND |
| Yellow / DATA | GPIO32 |

Add a 4.7 kOhm resistor between DATA and 5V.

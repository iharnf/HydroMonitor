# HydroMonitor

HydroMonitor is an ESPHome firmware project for a small hydroponic pH monitor.

Current target hardware:

- M5StickC Plus2
- PH-4502C pH interface board
- E-201 / PH-201 pH probe
- DS18B20 temperature sensor planned later

Version `0.1.0` is intentionally focused on the first safe test:

- boot the M5StickC Plus2
- connect to Wi-Fi and Home Assistant
- enable OTA
- read the PH-4502C analog output on `GPIO36`
- show filtered probe voltage in mV on the display

pH calculation is not enabled yet. First we verify stable real mV readings from the connected probe.

## Wiring

| PH-4502C | M5StickC Plus2 |
| --- | --- |
| VCC | 5V |
| GND | GND |
| Po | GPIO36 |
| Do | not connected |
| To | not connected |

The measured `Po` voltage was 2.7 V, so it is safe for the ESP32 ADC input in this build.

## First Flash

1. Copy `esphome/secrets.example.yaml` to `esphome/secrets.yaml`.
2. Fill in Wi-Fi values.
3. Open the project in ESPHome.
4. Install `esphome/hydromonitor.yaml` over USB.

After the first successful flash, future updates can use OTA.

## Roadmap

- `v0.1.0` - mV reading, display, Home Assistant, OTA.
- `v0.2.0` - pH calculation and two-point software calibration.
- `v0.3.0` - DS18B20 and temperature compensation.
- `v1.0.0` - stable release.

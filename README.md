# ESP LED Dimmer

## Overview

This repository contains the PCB files for a wireless dimmer for up to two monochromatic LED strips based on the ESP-01. It can e.g. be integrated into [Home Assistant](https://www.home-assistant.io/) using [ESPHome](https://esphome.io/).

The dimmer is powered via a DC barrel jack and supports both 12V and 24V LED strips. The LED strips are connected via screw terminals.

It is designed to make use of the PCBA services of JLCPCB and uses as many basic parts as possible. You can use the awesome [KiCAD JLCPCB tools](https://github.com/Bouni/kicad-jlcpcb-tools) for exporting the corresponding fabrication files.
Excluding the ESP-01 module, the cost per assembled PCB is around 5€.

> **Warning:** Only power up the dimmer when the ESP-01 module is plugged in, otherwise it might get broken! This seems to be due to the power supply IC requiring a certain minimum current to be drawn.

## Using the dimmer with Home Assistant

To use the dimmer with Home Assistant, create a new ESP8266 device in the [ESPHome Device Builder](https://esphome.io/guides/getting_started_hassio.html) and append the following lines to its YAML file:

```yaml
output:
  - id: led1
    pin: GPIO2
    platform: esp8266_pwm
    frequency: 1000 Hz
  - id: led2
    pin: GPIO0
    platform: esp8266_pwm
    frequency: 1000 Hz

light:
  - output: led1
    name: "LED 1"
    platform: monochromatic
  - output: led2
    name: "LED 2"
    platform: monochromatic
```

Install the resulting configuration to the ESP-01 and insert it into the corresponding header on the dimmer.
Within a minute the dimmer should be available within Home Assistant.

## License

This project is licensed under the MIT license, see [`LICENSE.txt`](LICENSE.txt) for further information.

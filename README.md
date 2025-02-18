# ESP LED Dimmer

## Overview

This repository contains the PCB files for a wireless dimmer for up to two monochromatic LED strips based on the ESP-01. It can e.g. be integrated into [Home Assistant](https://www.home-assistant.io/) using [ESPHome](https://esphome.io/).

The dimmer is powered via a DC barrel jack and supports both 12V and 24V LED strips. The LED strips are connected via screw terminals.

It is designed to make use of the PCBA services of JLCPCB and uses as many basic parts as possible. You can use the awesome [KiCAD JLCPCB tools](https://github.com/Bouni/kicad-jlcpcb-tools) for exporting the corresponding fabrication files.
Excluding the ESP-01 module, the cost per assembled PCB is around 5€.

## License

This project is licensed under the MIT license, see [`LICENSE.txt`](LICENSE.txt) for further information.

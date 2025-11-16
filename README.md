# ESPhome TagTuner/writer
This project is a for of [larcster's repo](https://github.com/larcster/esphome_tagreader) and relies heavily on the work by [adonno](https://github.com/adonno/tagreader) and [luka6000](https://github.com/luka6000/TagTuner)

This version extends on larcster's versions by adding an encoder with button functionallity (play/pause, next, previous and restart playlist) 
It also removes the need for an automation in home assistant for music playback, as the ESP handles all the service calls on it's own.
The version also uses substitutions and scripts in a more extensive way than larcster's version.

# Hardware
* Wemos Lolin S3 Mini
* PN532 NFC Reader
* WS2812 LED
* EC11 Rotary Encoder

# Wiring
I have wired the tag reader to the S3 mini using SPI
| PN532 Pin | Lolin S3 Mini Pin | Notes                       |
|-----------|-------------------|-----------------------------|
| VCC       | VBus              | Use thick wires for this    |
| GND       | GND               | Use thick wires for this    |
| SCK       | GPIO12            | SPI clock                   |
| MOSI      | GPIO 11           | SPI data out                |
| MISO      | GPIO 13           | SPI data in                 |
| CS/SS     | GPIO 5            | Chip select                 |  

For the LED:
| LED Pin | Lolin S3 Mini Pin | Notes                                                                                             |
|---------|-------------------|---------------------------------------------------------------------------------------------------|
| 5V      | Vbus              | Can also be connected to an available VCC on the P532, the Lolin S3 mini only has one pin for 5V  |
| GND     | GND               | Again, can be connected on an available GND on the P532, but the lolin has two pins for GND       |
| Din     | GPIO2             |                                                                                                   |

For the encoder:
| Encoder Pin | Lolin S3 Mini Pin | Notes                     |
|-------------|-------------------|---------------------------|
| S1          | GPIO18            |                           |
| S2          | GPIO16            |                           |
| Key         | GPIO17            |                           |
| 5V          | Vbus              |                           |
| GND         | GND               |                           |

# Building
Either install ESPHome on your computer or build directly in Home Assistant's ESPHome Device Builder. 
Copy and paste only the "device_yaml.yaml", rename file to the desire entity name and configure variables.
The packages will be pulled directly from the repo by ESPHome.
Remember to modify secrets.yaml according to your network.

# Installation
I've had issues when trying the initial install from within Home Assistant's ESPHome Device builder, I kept getting a unexpected device type error.
Doing the initial install from the ESPHome CLI fixed the issue and further OTA updates worked from Home Assistant.
During the initial install you will probably need to hold in the "boot" button while connecting with USB to the computer for flashing. 






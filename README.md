# ESPhome Tagreader/writer
This project is heavily based on adonno's and luka6000's work, check it out: https://github.com/adonno/tagreader and https://github.com/luka6000/TagTuner

This repo includes two separate versions of the tagtuner/tagreader, one with an added rotary encoder with button and one without.
Both version extends on the original versions by allowing for more custom "tag types" (ie. file printing tags, color tags, ect). 
The version with the encoder doesn't rely on any automation in order to play music, as the ESP handles all the service calls by itself.

The version with an encoder uses substitutions and scripts in a more extensive way than that without.

It is still compatible with this blueprint: https://gist.github.com/luka6000/ec6406e44de3dff082dd7e22cedcff93

# Hardware
* Wemos Lolin S3 Mini
* PN532 NFC Reader
* WS2812 LED
* <u>Optional </u>
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

For the optional encoder:
| Encoder Pin | Lolin S3 Mini Pin | Notes                     |
|-------------|-------------------|---------------------------|
| S1          | GPIO18            |                           |
| S2          | GPIO16            |                           |
| Key         | GPIO17            |                           |
| 5V          | Vbus              |                           |
| GND         | GND               |                           |

# Building
Either install ESPhome on your computer or build directly in Home Assistant's ESPhome Device Builder. Remember to modify secrets.yaml according to your network.


# Installation
You might need to hold in the "boot" button while connecting with USB to the computer for flashing. This is not necessary when doing OTA updates.






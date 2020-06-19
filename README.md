# Sapphire Pi Config.json


## Top Level

To generate unique identifiers for this homebridge instance, the Pi's name Sapphire was:

Converted from ASCII to HEX and used for all values except the port, which Converted from ASCII to t9 number up to 2^16
* username: up to six pairs of hex digits


## Auto-Run

With a chron jobs:
```
0 0 * * * pkill homebridge && /usr/bin/homebridge
@reboot homebridge &
@reboot python /home/pi/Desktop/Networked-Button/networked_button.py &
```

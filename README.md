# Sapphire Pi Config.json

### Unique Homebridge Instance Identifiers
Homekit Bridges require unique idientifiers to be added to your home. We make a deal of this because these identifiers can easily collide with other devices if you're not careful. To be safe use the name of your Pi/Computer to generate unique hombridge instance Identifiers. You should re-name your Raspberry Pi (or whatever computer you're using) Our house uses gemstone names for our Pi, hence "Sapphire Pi" See [homebridge-config-sapphire/config.json](https://github.com/banjioyewole/homebridge-config-sapphire/blob/master/config.json) for specifics.


### Conversion Schemes

#### ASCII to HEX Conversion Scheme
The ASCII to HEX conversion scheme is as follows: take the plain text name of your device, and convert it to hex digits. 

#### ASCII to T9 Conversion Scheme
The ASCII to T9 conversion scheme is as follows: Take the plain text name of your device and convert it to the numbers corresponding to the letters on the T9 Dialer pad. (Think 866-66-FASTER "You've Got the Green Light" -> 866-66-327837) 

### Required Unique Identifiers

#### Homekit Bridge Username
The Bridge's Username is a Hex sequence in format `HH:HH:HH:HH:HH:HH` You can use the ASCII to HEX conversion shceme to generate this username. 

#### Homekit Bridge Pin
Homekit Bridge Pins have format `XXX-XX-XXX`
Use the ASCII to T9 conversion scheme to generate this pin.

#### Homekit Port Pin
Homekit Bridges also have a specified port in format `int < 2^16`
Use the ASCII to T9 conversion scheme to generate this port, stopping below a value of 2^16.



## Auto-Run

With a chron jobs:
```
#0 0 * * * pkill homebridge && /usr/bin/homebridge
@reboot homebridge &
@reboot python /home/pi/Desktop/Networked-Button/networked_button.py &
```

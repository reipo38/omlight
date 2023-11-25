# omlight
bash script for controlling omen keyboard lightning using pelrun's kernel module

# Dependancies
This script ENTIRELY depends on [pelrun's kernel module](https://github.com/pelrun/hp-omen-linux-module) for the HP Omen, which is HIGHLY EXPERIMENTAL:
The module creates a virtual directory called rgb_zones inside /sys/devices/platform/hp-wmi which is created again EVERY TIME on BOOT and is owned by root. in order for this 
script to work the rgb_zones directory has to be owned by the user. I am yet to figure out how to do that and when I do I will create an installation scripts that sets it up and 
adds the script to the USER BINARIES for easy access.

# Usage
This program has 3 main functions. which are called right after the name of the program.
## wave
this function uses a mainloop, meaning if you want to close the terminal after calling it you have to append "&" to the line
it has two flags:
### -m/ --manual
you have to enter three colours you want the wave function to loop through either by hex or by the name of the colour if supported (red, green, blue, purple, yellow, cyan, lime, orange, pink white)
```
./omlight wave -m red green blue
```
### -p/ --preset
you can choose between a few ready presets each containing 3 shades of the colour that the preset is named after (red, green, blue, purple, yellow, cyan, lime, pink)
```
./omlight wave -p red
```
## stat/ static
you have to enter one hex or one supported colour that will be applied to the whole keyboard
```
./omlight stat red
```
## ind/ individual
you have to specify the zone that you want to change the color for and then enter a hex or a supported colour
```
./omlight ind red
```

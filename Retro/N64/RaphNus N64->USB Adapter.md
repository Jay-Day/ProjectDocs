Use QMK Toolbox

select firmware

ATmega32U4

Auto Flash

Short the pins with twezers or something

connect to usb C

disconnect after a second or two

flashing should happen automatically

USB-C Pro Micro


```sudo avrdude -v -p atmega32u4 -c avr109 -b 115200 -P /dev/ttyACM0 -U "flash:w:/home/jd/Desktop/gcn64usb.hex"```

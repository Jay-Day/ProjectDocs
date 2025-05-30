USB-C Pro Micro

``` jd@jd-desktop:~/Downloads/gcn64tools/src$ sudo avrdude -v -p atmega32u4 -c avr109 -b 115200 -P /dev/ttyACM0 -U "flash:w:/home/jd/Desktop/gcn64usb.hex"```
``` jd@jd-desktop:~/Downloads/gcn64tools/src$ ./gcn64ctl -f --set_mode 17 ```
unplug and replug

check in

USB-C Pro Micro

GND   -  GND

Data  -  3

3.3v  -  VCC

P2    -  RXI

``` jd@jd-desktop:~/Downloads/gcn64tools/src$ sudo avrdude -v -p atmega32u4 -c avr109 -b 115200 -P /dev/ttyACM0 -U "flash:w:/home/jd/Desktop/gcn64usb.hex"```

``` jd@jd-desktop:~/Downloads/gcn64tools/src$ ./gcn64ctl -f --set_mode 17 ```

unplug and replug

check in ./gcn64ctl_gui if it shows the adapter type

![image](https://github.com/user-attachments/assets/29dd2933-ae6a-4bbd-b57b-337c7a29ec5d)

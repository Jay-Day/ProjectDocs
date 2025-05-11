# Melee
Using an input integrity adapter, I followed the topics [here](https://github.com/Munseaux/Gamecube-Adapter-Slippi-Launcher-Linux-Install)
Using sudo, create a file called `/etc/udev/rules.d/51-gcadapter.rules` and paste `SUBSYSTEM=="usb", ENV{DEVTYPE}=="usb_device", ATTRS{idVendor}=="057e", ATTRS{idProduct}=="0337", MODE="0666"`
Reload udev rules with: `sudo udevadm control --reload-rules` replug your adapter after you do this.

# 64
Using a raphnet adapter for this one and Rosalie's Mupen Gui Emu
Installed both of these (sudo apt install)
libhidapi-dev
libhidapi-hidraw0
Copied both of these files to udev rules directory
HERE and HERE
Reload udev rules with: `sudo udevadm control --reload-rules` replug your adapter after you do this.

I've also gotten KSE to work with Steam successfully
Adding it as a non steam game with the proton 10.1 compatibility layer
****![image](https://github.com/user-attachments/assets/54a5facb-ab77-4818-aaca-fbb07895d3c6)


It's actually been more stable than Windows lol
![image](https://github.com/user-attachments/assets/6d187883-8a96-4e28-859b-9df323a0fdd5)


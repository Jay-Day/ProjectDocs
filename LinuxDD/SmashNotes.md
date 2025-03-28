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

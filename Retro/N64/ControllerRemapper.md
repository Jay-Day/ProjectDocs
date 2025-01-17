# N64 Remapper

## Source Repository
https://github.com/ZenithControlLabs/N64_Remapper
## Overview
This is, in my opinion, one of the coolest things I've seen lately for the N64 Community in terms of controllers but what is it exactly and what does it do?

It is an in-line controller remapper and gate configuration tool that utilizes a raspberry pi pico.


![PXL_20250117_181809854](https://github.com/user-attachments/assets/fc4b1214-7d86-445b-a310-95af77bf349f)

![image](https://github.com/user-attachments/assets/ce0464de-f2e9-465a-ac5b-fd1dc8681e6a)

![image](https://github.com/user-attachments/assets/0aab3dd8-a842-44fb-a090-142444da0a30)

## Things you need:
1 x Raspberry Pi Pico
1 x N64 Controller Extension Cable
1 x Micro USB Cable
1 x Soldering Capability 

![image](https://github.com/user-attachments/assets/41d866d8-38c4-4481-b22a-453fc85ccc99)

![image](https://github.com/user-attachments/assets/badd9894-d2e5-400f-98e7-cbc658c9557d)


## My Build Process
### Flashed the pico with Firmware

1. Download the firmware https://github.com/ZenithControlLabs/N64_Remapper/releases/tag/v0.1.0 
(You want the .uf2 File)
2. Hold in the Bootsel button on the pico and plug it into your PC
3. You'll see a mass storage device show up called RPI-RP2
4. Drag or copy and paste the file to the root of the mass storage device
5. If flashed correctly the device should disappear from the file explorer

### Soldering the wires
1. I decided to cut my extension cable right down the center. I may make a different design of a controller plug in the future where this board plugs into the end cap or a controller memory card slot but that's for another adhd ridden day.
2. strip a bit of the rubber away and get to soldering
3. Here's a map of where you need to connect your cables to. the colors should line up exactly
   ![remapper_pinout](https://github.com/user-attachments/assets/cbf25728-167b-4014-8d40-33b46892612a)
   Personally I had a bit of a hard time figuring out what end needed to be soldered where but basically... the end that plugs into your controller is the "Controller Data" and the end that plugs into your console is the "Console Data"
   I know, it seems like a stupid thing to mess up but if it happened to me I bet it happens to someone else.
   
### Using
1. You **must** use Chrome for this part of the project.
2. If you're on Linux, install the udev rules in this repo to /etc/udev/rules.d. Run sudo udevadm control --reload and replug.
   `SUBSYSTEM=="usb", ATTRS{idVendor}=="7318", ATTR{idProduct}=="0001", MODE="0666", GROUP="plugdev"`
   
   `SUBSYSTEM=="hidraw", ATTRS{idVendor}=="7318", ATTRS{idProduct}=="0001", MODE="0666"`
   
   `SUBSYSTEM=="usb", ATTRS{idVendor}=="7318", ATTR{idProduct}=="0002", MODE="0666", GROUP="plugdev"`
   
   `SUBSYSTEM=="hidraw", ATTRS{idVendor}=="7318", ATTRS{idProduct}=="0002", MODE="0666"`
5. Open Chrome
6. Plug your N64 controller into the pico
7. Plug your pico into the computer and you might see a popup from chrome, click it and click Connect Controller
8. Alternatively Navigate here https://zenithcontrollabs.github.io/Zenith_FW/web/platforms/remapper/
   
### Calibration (From Source Repo)
To calibrate, hit "Start Calibration" in the config tool and move the stick around the gate to the point instructed by the white circle. So, if the circle is in the center, let go of the stick. If it's in up right notch, move the stick to up right notch. After each step hit "Next step", until you've reached the end of the sequence. Then you should see the black & white circle move.

Some tips for a good calibration:

    Don't press super hard, or super light when moving into the notches. Press however hard you normally would when you move the stick into the notches.

    Don't let go immediately after hitting next step. There is some delay between you hitting the button and the stick signal being collected, so doing this risks collecting bad data from after you hit the button.

Once you're satisfied with the values from your calibration, make sure to hit "Save Settings" so it persists. You can now plug in the remapper to the console and it should work. Unplug the USB when you do this.

## My Personal experiences and use case.

Personally, I set my ranges to be a little extended as I don't put a ton of pressure on the gate when moving left/right/etc. 

I hear this also helps with DI in Smash.

![image](https://github.com/user-attachments/assets/dcbbf334-b784-4635-aeff-828fc617d75c)


I like to remap the R button to Z and vice-versa because I's rather Z cancel this way.

![image](https://github.com/user-attachments/assets/be054b5c-69ad-4e8b-89b0-97ad4fefe629)


If you notice the green dot on the notch remapper, that's the actual analog data that your controller is going to give the remapper (or console without this tool) the white circle is the location that gets sent to the console.

![image](https://github.com/user-attachments/assets/7c7fcf69-1f37-4145-93c0-84efe64dc55a)

How Angle Deadzones work:

It seems like even if you have the stick up to 20 points off of the notch, it will stick to that point on the output.

![image](https://github.com/user-attachments/assets/28ce3f4d-ec8d-4da5-8840-ec3fe9e023e8)



A screenshot of the debug screen in Smash Remix side by side the configuration screen

![image](https://github.com/user-attachments/assets/947b0b3f-5f0d-489f-83e6-63a4addfb80b)

Wonky thing that Boom pointed out, if you exceed 128 on the ranges it looks like it goes to the other side of the gate

![image](https://github.com/user-attachments/assets/7e61b116-8f2a-46d8-b089-d4e058391d09)



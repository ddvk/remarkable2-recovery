# reMarkable 2 Recovery / Unbricking

Tools for recovery (works only under Linux)


## Prerequisites

To put the rM2 in recovery, you will need:
- USB-C breakout board
- Pogo pin adapter to usb
    the pogo pins are as follows,  when viewed from the side, device facing up (VBUS is near the usb-c)
    `GND,ID,D+,D-,VBUS`

- [imx_usb_loader](https://github.com/boundarydevices/imx_usb_loader) a binary is included, but feel free to compile it


![Pogo](images/pogo1.jpg)
![USB-C Breakout](images/usb1.jpg)


## Recovery Mode
* run `dmesg -w` on your host to monitor
* power off the device
* connect the USB-C breakout board
*   pull down **B8** (connect a 10K resistor to GND)
* connect the pogo pins to the tablet and to the host usb
* **make sure the connection is good, use a short good, different cable, etc**
* if the device does not start on its own, press the Power Button
* you should see a new device *USB HID v1.10 Device [Freescale SemiConductor Inc  SE Blank ULT1]*
* remove the pulldown resistor (disconnect B8)
* run `./imx_usb`
* should see *USB Mass Storage device detected*
* should see a new mountable block device





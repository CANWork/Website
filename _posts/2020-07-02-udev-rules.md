---
date: 2020-07-02
title: Keeping Multiple CANWorks Straight
categories:
  - Tutorials
author_staff_member: CANWorkSupport
---
## Linux Only

If you are using multiple CANWork devices with the candleLight firmware, you may want to use udev rules to assign each serial number a fixed socketcan device name (can0, can1, etc) that persists between reboots and plugging/unplugging the device. This is easy with udev rules.

First, create a new udev rule file such as: /etc/udev/rules.d/99-candlelight.rules

This file will contain your rule. Place the serial number of your device (check dmesg after plugging it in, or use the usb-devices command) and desired device name in this file. No other values need to be changed. Add a line to this file for each device you would like to configure. 

SUBSYSTEM=="net", ATTRS{idVendor}=="1d50", ATTRS{idProduct}=="606f", ATTRS{serial}=="000C8005574D430A20333735", NAME="can5"
SUBSYSTEM=="net", ATTRS{idVendor}=="1d50", ATTRS{idProduct}=="606f", ATTRS{serial}=="000D8005574D430A20333735", NAME="can6"
SUBSYSTEM=="net", ATTRS{idVendor}=="1d50", ATTRS{idProduct}=="606f", ATTRS{serial}=="000E8005574D430A20333735", NAME="can7"

It is a good idea to set the device name to can3 and higher, as devices without udev rules will still enumerate as can0, can1, etc.
 
Reboot your system or run the following commands and unplug/replug your device and the udev rule will assign the interface number after enumeration.
sudo udevadm control --reload-rules && sudo systemctl restart systemd-udevd && sudo udevadm trigger


## Windows
Windows enumerates as device 0,1,2....

## OSX
TBD

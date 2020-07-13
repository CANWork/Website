---
date: 2020-07-01
title: Getting Started
categories:
  - Tutorials
author_staff_member: CANWorkSupport
---
Basic instructions for getting CANWork connected and running

**Termination**
Determine if you need to use the CANWork's onboard termination. 
CAN bus requires a 120 Ohm terminating resistor on each end of the bus for proper operation, and a completely unterminated bus will not function at all. 
The CANWork has a built in terminator you can use, but if your bus is already terminated make sure to disable onboard termination.

...Picture here...

**Connect To The Bus**
Connect the CANH, CANL, of your CANWork to your target CAN bus.
GND can be left open IF the USB-C ground is common to the other CAN bus devices.
Otherwise, connect GND to a common ground with other devices on the CAN bus.

...Picture here...

**Connect to the Host**
Connect your CANWork to your host devices USB port with a USB-C cable. Make sure you're using a good USB data cable and not a charge-only cable.

...Picture here...

**Basic Troubleshooting**

PWR/Tx LED:
  Bootloader: Always OFF
  Slcan:
  Candlelight:

Rx LED:
  Bootloader: Always OFF
  Slcan:
  Candlelight:

CANH:  
  wire color is typically yellow
  DB9 pin 7 

CANL:
  wire color is typically green
  DB9 pin 2
  
CAN bus speeds:
  OBD and cars typically 500k
  Heavy-duty trucks and J1939 are 250k
  
  

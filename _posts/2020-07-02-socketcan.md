---
date: 2020-07-02
title: SocketCAN
categories:
  - Tutorials
author_staff_member: CANWorkSupport
---
The CANWork provides a socketCAN-compatible interface that can be brought up with slcand. This allows you to use all standard Linux CAN utilities like candump, cansniffer, and even wireshark. 

Bus speed is specified with the "-s" parameter where:
-s0 = 10k
-s1 = 20k
-s2 = 50k
-s3 = 100k
-s4 = 125k
-s5 = 250k
-s6 = 500k
-s7 = 750k
-s8 = 1M

Just run slcand with the proper arguments (????????) for your bus speed, and a new CAN device should show up on your system. Don't forget to bring the interface up with ifconfig after running slcand! Now you can use any of the standard Linux CAN utilities to interact with the bus. Make sure that you specify the right TTY port, which you can check with the dmesg command after plugging in your CANWork.


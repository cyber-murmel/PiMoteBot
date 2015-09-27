#PiMoteBot

The goal of this porject is to get a Raspbery Pi up and running with a webserver over which you can controle the motors and watch a live camera stream.

## Setup

To keep it easy I use  the [Raspbian Server Edition](http://elinux.org/RPi_Distributions#Raspbian_Server_Edition), which is a lightweight version of Raspbian, but in case this link isn't working any more normal raspbian is also fine.</br>
First we need to download the latest version of Raspbian.
```
$ wget https://downloads.raspberrypi.org/raspbian_latest -O raspbian.zip
$ unzip raspbian.zip
```
Then we insert the SD into the computer, check for the drives name and flash the image. In this example it will be `sdc`.
```
$ lsblk
sda                 8:0    0 149.1G  0 disk 
├─sda1              8:1    0   243M  0 part # 
├─sda2              8:2    0     1K  0 part # my drive
└─sda3              8:3    0 148.8G  0 part #
sdc                 8:32   1   3.7G  0 disk  
├─sdc1              8:33   1    56M  0 part #
└─sdc2              8:34   1   3.7G  0 part # the SD card
sr0                11:0    1  1024M  0 rom 
$ dd if=raspbian.zip | p -b | sudo dd of=/dev/sdc bs=128M ; sync
```
This is the SD card ready. Plug it in, but don't power up yet. For the first time setup you can either connect a display and keyboard, wire connected to the local network, try to get the Ip and connect via SSH or connect to it via UART/Serial.

## UART

If you live in Germany like me, you can buy [this USB UART adapter](www.amazon.de/dp/B008AGDTA4/).

| wire        | GPIO        |
| ----------- | ----------- |
| black (GND) | pin 6 (GND) |
| green (RX)  | pin 8 (TX)  |
| white (TX)  | pin 10 (RX) |
| red (+5V)   | (leave out) |

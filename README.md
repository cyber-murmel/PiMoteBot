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
$ dd if=raspbian.zip | p -b | sudo dd of=/dev/sdc bs=128M ; sync
```


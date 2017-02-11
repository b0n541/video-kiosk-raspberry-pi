# video-kiosk-raspberry-pi

This is a description on how I created a video kiosk system based on a Raspberry Pi for our local museum in Groitzsch.

## Install Pixel OS

Just follow the official documenation:

https://www.raspberrypi.org/learning/software-guide/quickstart/

Copying the OS image to the SD card is done like this

```
sudo dd if=2016-11-25-raspbian-jessie.img of=/dev/sdb bs=4M
```

## First steps

* Changed locale
* Changed password for user pi
* Raised CPU clock for faster booting
* Update system

## Configured resolution for old monitor 1280x1024

This can be done more easily in the command line config tool: raspi-config

## Install Video looper

Instead of crafting my own video looper I just used this one:

https://learn.adafruit.com/raspberry-pi-video-looper/overview

I configured the source of the videos to be read from the SD card.

## Backup SD card

After everything was set up I made a backup of the SD card to recreate it again in case of something gets corrupted:

```
sudo dd if=/dev/sdb bs=4M | gzip -c > raspberry-pi.img.gz
```

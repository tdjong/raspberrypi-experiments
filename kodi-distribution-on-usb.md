# Getting a Linux distribution with Kodi for Raspberry Pi on USB drive
Several distributions exist (OpenElec, LibreElec or OSMC) for Raspberry Pi. 
The Pi requires to boot from SD card. However to limit writes to SD card, I want to run and write to a USB drive instead of the micro-sd card.

## OSMC - FAQ - Boot off an USB drive or NFS

Yes, they even build the option into the installer.
However the correct option to choose during the installer is not clear.
[Blog post explaining this option](http://www.averagemanvsraspberrypi.com/2015/10/install-osmc-on-a-usb-stick.html)

### Background for booting from different device

cmdline.txt contains bootloader parameters

boot=/dev/mmcblk0p1 tells OpenELEC the partition which contains the kernel.img and SYSTEM file. It is also possible to use partition labels (boot=LABEL=System) or UUID (boot=UUID=<insert_your_uuid>) or to boot over the network (PXE)

disk=/dev/mmcblk0p2 tells OpenELEC the “Storage” partition. It can also use partition labels (disk=LABEL=Storage) or UUID (disk=UUID=<insert_your_uuid>) or boot over the network (PXE)

Sources:

* https://osmc.tv/wiki/raspberry-pi/frequently-asked-questions/
* https://forum.libreelec.tv/thread-589.html

## USB drive needs more power

Standard the USB port supplies 0.6 A, which is not enough for some USB powered devices.
The Pi is capable of doubling that by changing/enabling a setting in /boot/config.txt 

################################################################################
# USB power level
################################################################################
 # default USB power is 0.6 mA
 # with max_usb_current = 1 an extra 0.6 mA is possible, allowing external USB disk storage
  max_usb_current=1
################################################################################

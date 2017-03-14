Problem: SD card or USB card corruption
Causes:
* too many writes for device
* writing during hangup or shutdown

Ideas:
* overlay ramdisk for writes with unionfs or something
* remove updates to fs by mounting with noatime
* add a power switch that tries safe shutdown first before losing power
* 

Sources:
* [Search results](https://duckduckgo.com/?q=prevent+disk+write+raspbian)
* [Improve Disk performance on Pi](https://www.linux-toys.com/?p=1153)
* https://www.raspberrypi.org/forums/viewtopic.php?f=29&t=20505
* http://ideaheap.com/2013/07/stopping-sd-card-corruption-on-a-raspberry-pi/

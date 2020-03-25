# Raspberry Pi Desktop running in Oracle's VirtualBox instead of the actual device:
1. Download a Raspberry Pi Desktop ISO (takes 2 hours?):
https://www.raspberrypi.org/downloads/raspberry-pi-desktop/
2. Download and install:
https://download.virtualbox.org/virtualbox/5.2.26/VirtualBox-5.2.26-128414-Win.exe
3. Following: http://www.aoakley.com/articles/2017-07-04-raspbian-x86-virtualbox.php
https://thepi.io/how-to-run-raspberry-pi-desktop-on-windows-or-macos/ Debian (64-bit)
4. Machine->New...
```Name: RPiDesktop
Type: Linux 
Version: Other Linux (32-bit) 
Memory size: 1024MB
``` 
5. Select Create a virtual hard disk now 
6. Select VDI (the default) 
7. Select Dynamically allocated (the default) 
8. Select 16GB
9. Machine->Start->Normal Start
10. Select start-up disk 2018-11-26-rpd-x86-stretch.iso (2.36 GB)
11. Choose Graphical install
```
Run with persistence
Run and reset persistence
Run without persistence
*Graphical install
Install
Install with speech synthesis
Help
```
12. American English
13. Manual
14. SCSI1 (0,0,0) (sda) - 17.2 GB ATA VBOX HARDDISK
15. Yes
16. pri/log 17.2 GB FREE SPACE
17. Automatically partition the free space
18. All files in one partition (recommended for new users)
19. Finish partitioning and write changes to disk
```
-Notes:	Debian 9
-Primary 7.5 GB ext4 /
-	logical 1.1 GB swap swap
-Primary 254.8 MB ext2 /boot
-        6GB      ext4 /
```
20. Yes (takes a handful of minutes)
21. Yes (to GRUB)
22. /dev/sda (ata-VBOX_HARDDISK_VB...)
23. 
Not needed:
"Devices->Optical Drives->Remove disk from virtual drive
Force umount"
24. 
Continue:
```
*Debian GNU/Linux (default)
```
25. Next
26. Canada
27. Canadian English
28. Toronto 
29. Use US keyboard
30. Password change -> leave blank
31. Update Software? -> Skip
32. Reboot
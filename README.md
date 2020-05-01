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
23. Not needed: "Devices->Optical Drives->Remove disk from virtual drive
Force umount"
24. Continue:
```
*Debian GNU/Linux (default)
```
25. Next
26. Canada
27. Canadian English
28. Toronto 
29. Use US keyboard
30. Password change -> pi, pi
31. Update Software? -> Skip
32. Restart
33. Navigate via the start menu in the top left corner to Internet > Chromium Web Browser
34. Go to myfiles.humber.ca to get files from your H:/ drive
35. Navigate to Accessories > Terminal
36. Run the command
```
sudo apt-get install codeblocks vim -y
```
37. To enable file transfer from your physical host computer:   
38. I haven't had a chance to make a set of instructions for shared folders (feel free to create them and let me know) or localhost networking/guest additions (feel free to create them and let me know) but you can use myfiles.humber.ca as a transfer place or enable USB key transfer as follows:
39. Shut down the guest virtual machine.
40. Properly eject any USB keys. 
41. In VirtualBox, go into the Settings of the guest virtual machine (Ctrl+S).   
![VirtualMachineSettings](https://raw.githubusercontent.com/six0four/ceng153/master/images/VirtualMachineSettings.png)
42. Select the USB filter with the blue circle icon and then click OK.   
![VirtualMachineUSB](https://raw.githubusercontent.com/six0four/ceng153/master/images/VirtualMachineUSB.png)
43. Start the guest virtual machine.
44. If you insert a USB key it should provide a dialog that it is inserted in the virtual machine.   
![VirtualMachineUSBinserted](https://raw.githubusercontent.com/six0four/ceng153/master/images/VirtualMachineUSBinserted.png)
45. Properly eject it from the virtual machine then shutdown the virtual machine.
46. Insert it back in and the physical host machine should recognize it.
47. Be careful not to leave USB devices plugged in while starting since if you allow your guest to connect to your USB drive that is currently mounted on the host, when the guest is activated, it will be disconnected from the host without a proper shutdown. This may cause data loss. 
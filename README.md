# USBForensic
Implementation of Autopsy data recovery on a corrupted USB Fedora OS rpi drive

#Process in Summary
I have been working with various Linux OS distros on RPI 4B from a USB Thumb Drive.  One installation of Fedora got corrupted and would not boot.
I am attempting data recovery and using Autospy on a Kali Linux system to gain more hands-on experience with Forensics and Data Recovery.
Steps:
1. I did not use a read only system like one does for a real forensic examination.
2. To create the image I used the Linux command "dd if=/dev/sda3 of=/home/user/fedcrasdb3.img conv=noerror,sync".
3. I did hash the original partition with SHA (/dev/sda3) and I hashed the image file I created as well and they matched.  

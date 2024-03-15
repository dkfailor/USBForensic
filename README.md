# USBForensic
Implementation of Autopsy data recovery on a corrupted USB Fedora OS rpi drive

 next I am not examining the img file on the same computer so i need to do a hash of the img after I move it to another portable drive to move to the examining computer.
One the sha hash is verified, the examining computer is kali based.  I assume from documentation that it will be read only but in a real forensics exam i would want to continue to write block all interactions with the img file and document with witnesses the process of transfer (chain of custody).
Blanked (formatted as ext4) USB drive and created Images folder to store and transfer to another computer.  Should have done a military wipe of the USB first to insure no corruption.  Also it might have been a good idea to create the original img files in a separate folder because I used cp “*img” to the USB drive and in retrospect, if there were any other “img” files there it would have copied them as well.  I like to keep everything separate in its own “container”.
from linuxconfig.org, “foremost utility tries to recover and reconstruct files on the base of their headers, footers and data structures, without relying on filesystem metadata. This forensic technique is known as file carving”
I was able to get some data but not nearly as much as I expected no matter if I used specific file types or wide open.

I have been working with various Linux OS distros on RPI 4B from a USB Thumb Drive.  One installation of Fedora got corrupted and would not boot.
I am attempting data recovery and using Autospy on a Kali Linux system to gain more hands-on experience with Forensics and Data Recovery.
Steps:
1. I did not use a read only system like one does for a real forensic examination.
2. To create the image I used the Linux command "dd if=/dev/sda3 of=/home/user/fedcrasdb3.img conv=noerror,sync".
3. I did hash the original partition with SHA (/dev/sda3) and I hashed the image file I created as well and they matched.  
4. I transferred the img files to a formatted USB drive but in retrospect I should have written military grade zeros to make sure it was completely wiped.  However I was able to do another hash after the files were transferred and they matched.
5. I plugged the USB into the rpi but again, did not use read only on the Kali System. Another hash would verify the integrity of the img files.

**#Change in Course**
1.  next I am not examining the img file on the same computer so i need to do a hash of the img after I move it to another portable drive to move to the examining computer.
One the sha hash is verified, the examining computer is kali based.  I assume from documentation that it will be read only but in a real forensics exam i would want to continue to write block all interactions with the img file and document with witnesses the process of transfer (chain of custody).
Blanked (formatted as ext4) USB drive and created Images folder to store and transfer to another computer.  Should have done a military wipe of the USB first to insure no corruption.  Also it might have been a good idea to create the original img files in a separate folder because I used cp “*img” to the USB drive and in retrospect, if there were any other “img” files there it would have copied them as well.  I like to keep everything separate in its own “container”.
from linuxconfig.org, “foremost utility tries to recover and reconstruct files on the base of their headers, footers and data structures, without relying on filesystem metadata. This forensic technique is known as file carving”
I was able to get some data but not nearly as much as I expected no matter if I used specific file types or wide open.
At this point I realized it would be much easier to install and use foremost to try and recover any of the docx, doc, pdf, txt, and html files I lost.  (Same considerations for forensics/chain of custody in a real file carve--my goal here was merely to retrieve some of the documents I lost).  However foremost only reovered some files even though I had immediately created the img file and did not use the drive before then.  Also the files all had numeric names so I had to open them to see what they were.
2.

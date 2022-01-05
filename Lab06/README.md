Name: Roman Gofer

Email: gofer.2@wright.edu

Part 1:

1. My Windows computer is running the Dell Inc. 1.13.0 version of BIOS. It is in the newer UEFI mode of BIOS. To find this information, I used msinfo. I opened this by right-clicking on the "start" button in the left-hand corner and hitting "run". In the window that popped up, I typed in "msinfo32". This displayed a whole window of information. I found the BIOS version in the "BIOS Version/Date" section, and the mode was found under "BIOS Mode".

2. The CPU is an Intel i5-1035G1 CPU. I found this by opening up the Task Manager and clicking on the "Performance" tab. Then, I clicked on "CPU". In this section, the CPU information was listed at the top of the screen.

3. My installed memory size is 8 GB, meaning the computer has 8 GB of RAM. This was also found using msinfo, and it was listed under "Installed Physical Memory (RAM)".

4. The total amount of virtual memory available is 16.8 GB. My system does have a pagefile that has 9.02 GB of space. The pagefile is an "overflow" area to put extra programs when the amount of RAM is running low. When the data is put here, it can still be brought back into the RAM if the user wants to start running it again. This concept is why programs just do not come right back up if a user maximizes it after it was minimized for a long time. In this case, the data was most likely transferred to the pagefile, and it takes some time to bring it back to the RAM.

5. There is one disk installed on my computer, and the file system for that is the NTFS file system. I found this by going into the File Explorer, clicking on "This PC", and then right clicking on the disk, "OS (C:)". After this, I clicked properties, and the window that came up listed the file system.

6. There is a partition labeled number 6, but I only counted 5 visible partitions. The main one is "OS (C:)" and the storage on that is 459.17 GB. This is the main partition of the one disk on my computer, where all content and files are stored, such as the pagefile and boot protocols. I found this by searching for the control panel. Once here, I clicked on Administrative Tools under System Security, and then I clicked on Computer Management, and "Disk Management" after that.

7. I accessed my UEFI BIOS by going to Settings > Update & Security > Recovery > Restart Now. Once the system restarted, an Advanced Startup screen came up, and I clicked on Troubleshoot > Advanced Options > UEFI Firmware Settings > Restart. After this restart, the computer was forced to open the UEFI BIOS screen.

Part 2: Exploration

1. It would present the default kernel options and the default kernel options for automagic boot. This is also changeable, and the user can change system settings to make it present special boot options for certain kernels. I read this file by doing cat /boot/grub/menu.lst.

2. Using the df -h command, I saw that the main disk for this machine, xvda1, has 3.4 gigabytes, or 44%, of its space used up, and 4.4 gigabytes are available. The total amount on this disk is 7.7 gigabytes.

3. The primary disk in the /dev folder is called Xen Virtual Block Device (xvd). It is using the Microsoft Disk Operating System partition table, which is an old-style system first released in 1981 and last released in 2000. This devices uses the ext4 file system.

4. Using lshw, I found that the BIOS version of the machine is the legacy BIOS. It has an Intel(R) Xeon(R) CPU E5-2676 v3 @ 2.40GHz CPU, and it has 1 gigabyte of memory.

5. No, this system does not have a swapfile/use virtual memory. I checked by typing cat /proc/swaps, which shows the swap devices currently being used. When I typed this command, no devices showed up, so that means the system is not using any swapfiles since there were none to display.

Part 3:

1. I accomplished this by typing git add Lab06 to add the directories for tracking, typing git commit -m to add a message describing the latest edits I made, and then I typed git push to upload my changes into my remote repository.



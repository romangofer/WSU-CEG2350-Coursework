Name: Roman Gofer

Email: gofer.2@wright.edu

Part 1:

1. "if" is what tells the system to read from the "zero" file in dev instead of the default, and "of" tells the system to write the output to a different file other than the default output file

/dev/zero is a file that just contains zeros. What this does is it helps create an empty file with no meaningful content, just zeros, but it still gives size to a file in order to reserve space on the disk.

A 1024 byte-size file was created, which is 1KB. The "bs=1024" part of the given line typed into the system is what specified that the block size of the file was to be 1024 bytes.

2. For this part, I used "sudo mkfs.ext4 /dev/space"

3. To accomplish this, I used "sudo mount /dev/space usable" To make the "usable" folder, I did mkdir usable.

4. /dev/loop6       93M  1.6M   85M   2% /home/ubuntu/usable
 
5. When I first made the files, I had to do "sudo vim NEW-FILE-NAME". Once I did this, I had to do "sudo chown ubuntu" on the file so I owned it and could write to it without using sudo.

6. To accomplish this, I used sudo umount /dev/space

7. No because I ejected the "partition" in which the files were located. Even though the files were inside the usable directory, they were inside the space partition. In order to access them again, I would have to remount the partition back onto the system.

8. After doing "strings /dev/space", I was able to see the contents of my file. It listed the path of my usable directory, and it listed my newfile.txt file. Also, it listed the swapfile that goes with my file. The other thing it listed were a whole bunch of weird, unreadable characters.

9. After deleting the file and unmounting again, I can still see the contents of my files when doing strings on the partition.

10. Here is what I added to /etc/fstab: /dev/space /home/ubuntu/usable ext4  defaults 0 0

The "mount -a" command automatically mounts all filesystems that are eligible for automount. 

When I use df -h after doing sudo mount -a, I can see that the filesystem was mounted. Also, when I head back to usable, I can also do ls and see all my other files that I did not delete. 

Part 2: 

1. I did this step with "git branch development"

2. For this part, I did git checkout development

3. See numbers 1 and 2

4. Visual check - it worked

5. I confirmed this

8. To switch back to my main branch, I used "git checkout main". To merge the development branch with main, I used "git merge development".

9. For this part, I used "git add Lab07", "git commit -m "Enter message here"", and then "git push" within the main branch.

Part 3:

1. See repository

Name: Roman Gofer

Email: gofer.2@wright.edu

Part 1:

1. When I ran python --version, the output was Python 2.7.17.

2. To download Anaconda on my AWS system, I used  wget https://repo.anaconda.com/archive/Anaconda3-2020.11-Linux-x86_64.sh

3. To compute the SHA-256 hash of the downloaded file, I used sha256sum Anaconda3-2020.11-Linux-x86_64.sh 

The sum that was output was cf2ff493f11eaad5d09ce2b4feaa5ea90db5174303d5b3fe030e16d29aeef7de

The above sum matched what was listed on the website.

4. The modified command I used to compute the MD5 sum to check the file's integrity was tail -n +589 Anaconda3-2020.11-Linux-x86_64.sh | md5sum -

The result of my command was a8f71d57955d4618ab3c1b02b963f667  - Yes, this result does match the result on line 379.

5. I started the installation by using "bash Anaconda3-2020.11-Linux-x86_64.sh". Once I did this, the system asked me to press "enter" and look over the terms and conditions. After looking over them, I had to type "yes" and hit "enter" again. After this, the system asked me to verify that I wanted Anaconda installed in /home/ubuntu/ by pressing "enter". After this, the script started executing.

6. The directory I installed Anaconda to was the /home/ubuntu/ directory. The full path is /home/ubuntu/anaconda3. 

7. The .bashrc file was modified when Anaconda was initialized by the installer.

8. When I did the cat command on the .bashrc file, I saw at the bottom that the installer appended a section for the Anaconda initializer. One of the things it added was an if-else statement that instructed the initializer to modify the PATH variable to have the path to the directory that has anaconda3 in it.

9. It recommends we restart the shell / logout and back in to "refresh" the .bashrc file and make the new changes take effect. When changes are made to the .bashrc file, they do not automatically take effect. The .bashrc file must always be "refreshed" for that to happen. When the shell is restarted, it automatically runs "source" on the .bashrc file in the background. Another way to "refresh" the file without restarting is to do "source .bashrc".

10. To update the shell, I did what the installer recommended, which was exit out of the current shell and log back in / restart it by doing exit and then aws-ssh, which made the system do "source" on the .bashrc file when it restarted.

11. When python --version was run, this is what was output: Python 3.8.5 
This shows the anaconda install was successful because the version of python on the AWS system was updated from version 2.7.17 to 3.8.5.

Part 2:

1. When I ran du -sh /home/ubuntu, it said the size of my ubuntu user's home directory on AWS was 110 mb.

2. When I ran man tar I was able to see the following information for all the flags:

-c: This creates a new archive. To archive something with this it would be tar -c hello.txt. Can also be done with directories, but they are archived recursively, unless the --no-recursion option is used.

-v: Verbosely list the files processed

-f: Uses the archive file or device archive. If this option is not used tar will first examine the environment variable 'TAPE'.

-z: Filters the archive through gzip(1) and compresses it.

-x: Extract files from an archive. Arguments are optional. If one is given, this flag will extract a specific file that was passed. 

3.  To create a tar ball of my space "file" in Lab07, I used the command  sudo tar -cvf space2.tar ubuntu/space ubuntu/git/spring2021-ceg2350-romangofer/Lab07

4. The size of the tar file is 101 mb when I run du -sh space2.tar.

5. When I cat the tar file, it is sort of readable. At first, it showed some paths and some weird strings of numbers. When I scrolled down to look at the restof the output, I was able to read the rest of the contents. When I made a tar file with the space file from Lab07, it also included the README.md file from the directory in that, so I was able to see the contents of this file when I ran cat on this tar file.

6. I used gzip to compress the tar file, and the command I used was sudo gzip space2.tar

7. The size of the gzip file is much smaller than the original tar file. The original file was 101 mb, and now, when I ran du -sh space2.tar.gz, the size of the file is showing as 104 kb.

8. MD5 sum: bad5ff0f18530d759bb279135e98d3e8 

SHA-256 sum: 0ce529c2ba1e7e45881c9e1d499fb17588a8c445440a3be2702765afd96c2110

9. I used sftp -i ceg2350privatekey.pem ubuntu@34.224.229.96 to connect to my AWS instance via sftp. To find the ssh command I use with my alias to get in with ssh, I did cat .bashrc | grep aws-ssh

10. To download the gzip file to my local system, I used get space2.tar.gz 
Also, I made sure I was in the home remote working directory where this file was located by using the usual commands like cd, pwd, and ls before attempting to download it. 

11. On the local system, the MD5 sum was bad5ff0f18530d759bb279135e98d3e8, and the SHA-256 sum on the local system was 0ce529c2ba1e7e45881c9e1d499fb17588a8c445440a3be2702765afd96c2110. Yes, the sums are the same as the sums computed on the AWS system.

12. To uncompress and extract the tar'ed and gzip'ed file on my local system, I used the command tar -xzvf space2.tar.gz

13. This doesn't work because the files installed on the local system are just a copy of the actual repository that is cloned on the AWS system, so this copy installed on the local system is just functioning like a directory, and not an actual git repository. In order to make the git commands like git push work on the local system, one would have to go through the process of cloning the actual repository onto the local system and setting up the ssh key for the git passwordless system where a password does not have to be entered to push items to the remote repository and do other functions like that.

Part 3:

1. The method / client I have been using to ssh in to my AWS system is MobaXterm.

2. To create the new ssh key on the client, I used this command: ssh-keygen -t ed25519 -C "gofer.2@wright.edu"

3. The ssh key was created in the .ssh directory on my local system.

4. On my client, the private key is the id_ed25519 file, and the public key is the id_ed25519.pub file. I can tell that the private key is the private key because it has this heading at the top of the file when I cat it: -----BEGIN OPENSSH PRIVATE KEY-----. As for the public key, I can tell the id_ed25519.pub file is the public key because it has the .pub extension on it.

5. Here is the full command I have been using to connect to my AWS system: ssh -i ceg2350privatekey.pem ubuntu@34.224.229.96

6. When I look at the "authorized_keys" file in the ubuntu user's .ssh directory, I do see the contents of a public key in there, and I also see the name of my private key that I linked to get into my AWS system listed in there.

7. What I did to copy my newly created public key over to the authorized_keys file in my AWS system's .ssh directory was on my local system I opened up the public key file and copied the contents of it. Then, I went over to the terminal connection that I connected to my AWS system on and pasted these contents into the authorized_keys file after doing "vim authorized_keys" to open it. I just left a line between the current public key in there and the newly appended public key contents.

8. My modified ssh command after creating the public/private key pair is ssh ubuntu@34.224.229.96. The -i flag/parameter is no longer needed in this case because the public/private key pair was created inside the system, so the keys were stored in a default location and given a default name. This way, ssh knows about this key automatically and can look at it on its own when it's time to ssh into the AWS system. The -i flag tells the system the private key needs to be read from a specific file, not just the default. This was needed when AWS generated a special private key file to download and put into the home directory. Now that the private key is just a default type of file, there is no need to tell the system what file to read the private key from, and it will just automatically read the private key file inside .ssh on its own.

Part 4:

1. To put the Lab10 folder in my GitHub remote repository, I did git add Lab10, git commit -m "Finished Extra Credit Part", and git push.

Extra Credit:

The first step I took to install ninvader on my AWS system was download the "ninvaders-0.1.1.tar.gz" file by doing "wget LINK-TO-FILE".

After this, I did "tar -xzvf ninvaders-0.1.1.tar.gz" to extract the files from the gzipped folder.

Once the files were extracted, I tried doing "sudo apt install ncurses", but that did not work for me. After doing some more research, I found a version of this ncurses library, and the place I found it said it was possible to download it with "wget LINK-TO-NCURSES", so I did that. It downloaded a gzipped folder with the ncurses library in it onto my VM.

Next, I extracted the files of the ncurses library from the zipped folder by doing "tar -xzf ncurses-6.1.tar.gz"

Upon completing this step, I did "cd ncurses-6.1" and ran "./configure --prefix=/opt/ncurses" to configure the library.

The next commands I ran were "make" and "sudo make install" to compile all the code in the library and install it.

Once the ncurses library was properly configured, I left the ncurses directory and headed over to the unzipped ninvaders directory. I did "ls" to see the contents of this directory and noticed there was a README file.

I looked at the directions in this README file, and it said the code needed to be compiled by typing "make" into the command line while inside the ninvaders directory. 

I ran the "make" command, and the code was compiled. The README file stated that the game/program could be run after being compiled by doing ./nInvaders.

I did ./nInvaders while still inside the ninvaders directory, and the game opened up successfully.



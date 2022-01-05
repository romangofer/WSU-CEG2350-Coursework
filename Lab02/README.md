Name: Roman Gofer
Email: gofer.2@wright.edu

1. The first step I took to switch my repository from HTTPS to SSH is generate a public/private key pair on my virtual machine by typing ssh-keygen -t ed25519 -C "gofer.2@wright.edu". Then, I took the public key that was generated and copied that into my github repository online. After this, I typed the following line in: git remote set-url origin git@github.com:WSU-kduncan/spring2021-ceg2350-romangofer.git. This allowed me to access my repository using the newly-generated key pair without having to enter in a username and password.

Part 1:

2. What happens to the path of Directory B is two directories were created when mkdir Directory B was typed in. If a user wants to put spaces in the name of a directory, they need to put quotation marks around the name because the system will think the user is trying to make a directory called "Directory" and another called "B". The better naming convention is to just make a name with no spaces in it or use underscores to separate different words in the name.

3. To rename my "Directory B" directory to "DirB" I typed in "mv 'Directory B' DirB".

Part 2:

1. I created a test.txt file in my DirA directory by typing "vim test.txt"

2. To type in three lines of text in this file I typed "i" for insert, and then I typed in the text. After I was done, I typed ":wq" to get out of the file.

Part 3:

1. I made a copy of test.txt by typing "cp test.txt .hidden.txt"

2. Same answer as #1

3. When I first typed ls, I could only see the original test.txt file. I used the ls command with the "-a" flag to see the .hidden.txt file.

Part 4:

1. For the files in DirA, the user has read and write permissions, the group also only has read and write permissions, and the "other" section currently just gives read permissions. The current owner and group names for the files are "ubuntu".

2. To complete this step, I typed "sudo cp test.txt su-test.txt" into the command line.

3. For the su-test.txt file, the user has read and write permissions, the group only has read permissions, and the "other" category only has read permissions as well. The current owner and group names are "root."

4. No, my user cannot write to the "su-test.txt" file because the permissions I listed in the previous question are only for the root user. I can write to the file without changing the permissions by typing "sudo" in front of "vim su-test.txt".

5. To give my user (ubuntu) I added writing permission to the su-test.txt file for the "other" category. I added this by typing "sudo chmod o+w su-test.txt" into the command line. After this, I was able to do "vim su-test.txt" with no sudo and then hit "i" to insert text. Before this, I got a message saying I did not have write privileges inside the file if I did not use sudo in the command line.

Part 5:

1. By default, ln followed by a filename gives an error message that says "ln: failed to create hard link './test.txt': File exists"

2. To do this step I typed "ln test.txt hard.txt"

3. The inode numbers of the test.txt file and the hard.txt file are both the same: 789257

4. To complete this step I typed "ln -s hard.txt sym.txt"

5. No, the inode number of sym.txt is 789255, and the inode number of hard.txt is 789257, so sym.txt has 2 fewer inodes than hard.txt.

6. After deleting test.txt, hard.txt and sym.txt are both still readable.

7. After deleting hard.txt, sym.txt was no longer readable. This is because sym.txt was a symbolic link to hard.txt. Symbolic links do not contain the data of the target file. Instead they just refer to another file that exists without containing the data of that file. A hard link actually contains the data of the target file to which it is linked,  which is why the hard link to the test.txt file was still readable after test.txt was deleted. Also, the inode number, which explains the data that is in a file, was different for the sym.txt file. This means this file did not have the same data as the hard.txt file to which it was linked.

8. Yes, it can be read now. This is because there is a concrete file with data in it for sym.txt to refer to. Before, there was no data for sym.txt to link to.

9. After moving hard.txt to DirB, I cannot read sym.txt.

10. For this step, I typed in "rm sym.txt"

11. I completed this step by typing ln -s git/spring2021-ceg2350-romangofer/Lab02/DirB/hard.txt git/spring2021-ceg2350-romangofer/Lab02/DirA/newsym.txt 
When I made this link across the two directories, I was not able to read the "newsym.txt" file. Conversely, when I made a symbolic link from hard.txt to sym.txt in only DirA, I was able to open up the sym.txt file and see the contents of the hard.txt file.

Part 6:

1. To complete this step, I typed git add Lab02 to add my Lab02 folder. Also, I typed git status to see all of the changes that needed to be committed. Then, I used this command : git commit -a -m "Added Lab02 folder to CEG2350 repository". After this, I put in my e-mail that I used with my github account, and I also put in my username to establish my identity. Once the system knew who I was, I ran the git commit command again. The last command I used was git push, which uploaded my new files so that they can be viewed on the github website. As for headaches, I did not really run into any along the way when going through this process. The only minor issue was when I had to enter in the e-mail address and username I used with my github account. Once I did this, everything else worked as it should. 


Name: Roman Gofer

Email: gofer.2@wright.edu

Part 1:

1. I completed this by using the "sudo apt install" command.

2. The /usr/share/dict/words file is the correct one that has all of the words in it. The second path given in the lab directions does not exist.

3. For the grep command, the -E option makes the system look for all of the regular expressions that might match the search that was entered in by the user. 
For example, the line grep -E "apple" /usr/share/dict/words would look for all of the expressions in the dictionary that have the letters "apple" somewhere in them. The -c option does counting. When looking for something specific in a dictionary file, it will count up all of the search results that came back according to the user's search parameters. This saves time, as it takes away the long list that would have been generated, which means manual counting is no longer necessary. The -i command ignores whether or not a word starts with an uppercase or lowercase letter and will retrieve words based on the parameters regardless of what case it is.

4. 18,061 words start with a vowel, including both uppercase or lowercase words. To do this, I used grep -Eci. E was to include everything, c was to count how many words fit the vowel criteria, and i was to make the system not pay attention to the case of the words. Then, I used the "\<" and "*\>" features to show I was looking for words that started with specific letters. Inside of this, I typed "aeiou" inside of brackets and the "[:alpha:]" feature to expand the search to all of the possible vowel letters. In the end, my final line I typed in was : grep -Eci '\<[aeiou][[:alpha:]]*\>' /usr/share/dict/words

961 words have the word "cat" inside of them. Here are the commands I used: grep -Eci "cat" /usr/share/dict/words

7,545 words in the words file have a non-alphanumeric character in the word. I used the grep command with -Eci to include everything, count all of the words, and ignore the cases of the words. Also, I used the \W command, which tells the system to search for all words containing any non-alphanumeric characters. This is what was typed into the command line:  grep -Eci \W /usr/share/dict/words

21,028 words in this file have at least one letter m in the word. As for the commands I used, everything was the same as the previous steps in this question, except I used 'm{1,}' to indicate that I was looking for all words that had at least one instance of the letter m in it. This was the line I typed into the command line: grep -Eci 'm{1,}' /usr/share/dict/words

Part 2:

1. To create the scripts folder, I made sure I was in my Lab04 directory, and then I typed mkdir scripts. After this, I did cd scripts and used vim to create the marco and polo scripts. Also, I put #! /bin/bash at the top of each script file.

2. To do this, I typed echo This is from marco and echo This is from polo into each respective script file.

3. To add the directory to my scripts to the path, I used the export command and the path that goes to my script files to add this path onto the end of the existing path. This was what I typed in:  export PATH=$PATH:/home/ubuntu/git/spring2021-ceg2350-romangofer/Lab04/scripts

The marco and polo scripts can now be run in any directory. To test this, I backed all of the way out of my git repository and ran my scripts successfully. After this, I went back into my repository. As I was going back in, I ran my script after I changed each directory, and it worked every time.

To make this path addition permanent, I opened up the .profile file with vim, and then at the bottom I copied and pasted the path to my script files. When done, I "refreshed" the .profile file by doing source .profile. After doing this, the scripts were still able to be run from any directory.

4. In order to complete this step, I typed in my marco script "pwd > /home/ubuntu/git/spring2021-ceg2350-romangofer/Lab04/scripts/output.txt" This makes the script print the working directory specifically to an output.txt file that is located in the "scripts" directory. Since this file is in the same directory as
the polo script, it also knows about the output.txt file and can refer to it. I wrote in the absolute path to the file so that the script knows which file to put the working directory into because this script can be run in any directory. If this script were to be run in any directory other than scripts with only a relative path to the file, then the system would not know which file is the output.txt file. Additionally, the ">" symbol is to redirect the printing of the working directory to the output.txt file.

5. I added this feature to the polo script by adding the following line of code: echo cd "$(</home/ubuntu/git/spring2021-ceg2350-romangofer/Lab04/scripts/output.txt)"

The echo command is what makes the script print the message. After this, the command to be displayed can just be typed in, which is cd, or "change directory."Then, the rest of this line of code is what allows the script to print the contents of the output.txt file, which has the absolute path to the directory the marco script was last called in.

Part 3:

1. Usage guide: Step 1: In any directory, type "marco" into the command line. Once this is done, the message "This is from marco" will be displayed.
                Step 2: This step can be completed in the same directory, but it is recommended that the system be moved into another directory for this step's functionality to be more noticed. To change directories, just type "cd" then hit the space key and type in another directory to move to, such as "git" or "Lab02".
Step 3: Once in another directory, type "polo" into the command line. The message "This is from polo" will be displayed, and on the line directly under this, the following will be displayed: "cd /path/to/directory", with the second part of this being the path to the directory the marco script was run in. 

Step 4: Highlight the message in the second line that has cd along with the path to copy it, and in the command line right-click to paste it in.

Step 5: Hit the "enter" key, and the system should move to the last directory the marco script was run in.

2. I used the "git add" command to add the files in my Lab04 directory for tracking, then I used the "git commit" command with the -m flag along with a description of what I did with the files I am about to push, and the name of my folder, Lab04, and then I used "git push" to transfer my Lab04 folder to github.
 

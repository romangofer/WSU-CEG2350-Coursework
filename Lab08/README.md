Name: Roman Gofer

E-mail: gofer.2@wright.edu

Part 1:

1. To complete this step, I did vim infinity to create the file, and then at the top of the file I typed in #!/bin/bash to specify
that this file was supposed to be a bash script. Also, I had to give myself permission to execute it by doing chmod u+x infinity.

2. To add the loop to the script, I used a while loop with the ":" command, which always evaluates to true, allowing the script to run indefinitely 
until the user stops it.

To make this script output "Still going!" to a file called still-going.txt, I wrote "do echo "Still going!" >> still-going.txt" under the "while :". Do tells
the loop what commands need to be executed, and I used I/O redirection to have the script automatically generate the "still-going.txt" file and append the message to it.

For the sleep part, I used the sleep command, which ended up being "sleep 15" for this assignment. Seconds are the default unit of time for this command, so just typing
a number after it will be enough to specify to the system that the time to sleep is in seconds. A user could add in "m" or "h" if they wanted it to sleep for a certain amount of minutes or hours.

Part 2:

1. The PID of the terminal I will monitor processes on is: 30055

   The PID of the terminal I will experiment with running my script is: 29583

2. To accomplish this step, I ran my script in my first connection, then in the other one I did "ps au" and found the PID that was listed next to "/bin/bash ./infinity." Then, I did "kill -15 30475". The -15 was to pass a signal to this job that I wanted everything terminated, and the 30475 was the PID of my script job running.

3. When running the script with source, the PID to the exact job of the script running is not listed, so killing the running of the script here will shut off the entire connection in the terminal. 

To kill the process, I used sudo kill -1 30901, with 30901 being the PID of the terminal's whole connection.

4. To run it in the background I ran it like normal, pressed ctrl+z to stop it, and then resumed it in the background by typing bg.

The PID for this case is 31095, and the job ID is 1.

To kill via the job ID, I used sudo kill %1.

Part 3:

1. To set up session, do screen. To run inside: ./infinity, To detach ctrl+a, then type d.
2. Yes it does know, it lists a PID for the script running job when screen -ls was typed.
3. screen -r 31390
4. ctrl+a to stop the script, and then k to kill the screen session

Part 4:

1. For this, I did vim marco and vim polo and referred back to my work from Lab04.

2. I went to my home directory and modified the PATH variable in my .profile file to have the absolute path to my Lab08 directory. To "refresh" it after making those changes, I typed in "source .profile". After this, the changes still did not update, and the script was still linking back to the Lab04 directory. To fix this, I ended up exiting out of my connection and just sshing back into my VM. After this, my changes updated and the PATH variable switched over to the Lab08 path instead of the old Lab04.

3. For this part, I added pwd > /home/ubuntu/git/spring2021-ceg2350-romangofer/Lab08/workingdirectory.txt into my script, which tells the script to redirect the output contents of pwd to a file called workingdirectory.txt for the polo script to reference.

4. For this part, I added cd "$(cat /home/ubuntu/git/spring2021-ceg2350-romangofer/Lab08/workingdirectory.txt)" to my polo script, which tells it to change to the directory that is listed in the output contents of "cat path-to-workingdirectory.txt".

5. In any directory, run the marco script by simply typing "marco" into the command line. The script will then display a message "This is from marco", indicating that the script was run successfully.

Next, change to another directory and run the polo script by typing "source polo". "Source" is required here because scripts run in the subshell. In order to tell the script to go to the parent shell, where the file with the path to where marco was run is located, the polo script needs to be run using source. It should also display a message, which is "This is from polo", indicating that the script was run successfully.

At this point, you should notice that the current working directory
was changed back to the one in which the marco script was run.

Part 5:

1. git add Lab08
git commit -m "Enter message here"
git push

Extra Credit: Conflict Resolution

I went with option A.

The command I used to push this branch to GitHub was "git push --set-upstream origin improvements".

Basically, this merge did not go through successfully. It is saying that the automatic merging failed.

When I head to my file, I see the >>>>>> symbols. I had to take these out and keep my other content from the other branch.

When I run git status, it tells me that I should do git add to keep my changes in main and merge them with the changes in improvements. Now that the conflict is resolved, I can merge the two branches together. 

To merge the improvements branch into main, I first made sure I was in the main branch. Then, I did git merge improvements. Once the merge was completed
successfully, I used git add to add in all of my new changes, git commit -m "Type message here" to summarize all of my new edits, and then I did git push to get everything out onto GitHub remote.

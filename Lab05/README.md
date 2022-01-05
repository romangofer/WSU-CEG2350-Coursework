Name: Roman Gofer

Email: gofer.2@wright.edu

Part 1:

1. Here is my code for my program: 

// C program to read strings

#include<stdio.h>

int main()
{
        // declaring string
        char str[50];

        // reading string
        printf("Enter a string:");
        scanf("%s",str);

        // print string
        printf("%s",str);

        return 0;
}



Part 2:

1. The location of gcc is /usr/bin/gcc. I found this by typing whereis gcc into the command line. The version of gcc that is running on my VM is version 7.5.0. The command I used to find this out was gcc --version.

2. The location of javac is /usr/bin/javac. I found this by typing whereis javac into the command line.  The version of javac that is running on my VM is version 11.0.10. The command I used to see this was javac --version.

3. I compiled my source code by typing " gcc repeat.c -o repeat.exe" into the command line.

4. I ran my compiled code by typing ./repeat.exe into the terminal.


Part 3:

1. I created a file called Makefile by typing "vim Makefile" into the terminal.

2. Here are the contents of my Makefile:

compiler = /usr/bin/gcc


default: repeat.c
        $(compiler) repeat.c -o repeat.exe

run:
        ./repeat.exe


clean:
        rm repeat.exe


Part 4:

1. To run the program manually, just type "./repeat.exe". After this, a string can be entered, and whatever is entered will then be displayed.

To use the make command, I made the default section of my file, which tells the system what to do by default whenever make is typed into the command line. The line under the default: repeat.c line is what tells the compiler, gcc, to compile my c source code into an executable file. In this case, I set the compiler here to name the executable file "repeat.exe". By making all of this the default, the user can easily do this in a shortcut way by just typing "make".

For the make run command, I made up a word that can be typed in, which is "run". Under this, I put in the command to run the executable, which is "./repeat.exe". Now, all the user has to do to run the program is type make run, instead of typing out the command to run a program.

For the make clean command, I did the same thing as the first two instances, except I made the shortcut word "clean". Also, I paired that with the command "rmrepeat.exe", which is what's needed to delete the compiled program. Now, make clean just needs to be typed to delete the compiled programs without having to manually type the command to delete each time.

2. To do this, I typed in "git add Lab05" to add my directory for tracking. Then, I used the git commit command like this: "git commit -a -m "Details of Changes". After committing, I used "git push" to push the changes out to github. 

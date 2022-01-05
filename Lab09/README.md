Name: Roman Gofer

E-mail: gofer.2@wright.edu

Part 1:

1. The network interface currently being used for my connection is the Wi-Fi LAN adapter interface on my computer.

2. MAC/Physical Address: 28-CD-C4-1E-B8-5B

3. System hostname: DESKTOP-PFAN6V0

4. IP Address of Machine: 192.168.1.88

5. Subnet Mask: 255.255.255.0

6. Gateway: 192.168.1.254

7. The IP for my machine is a private address, as it begins with 192.168, which is a standard way to label and allocate private IP addresses.

The command I used to find all of this information in my Windows system is ipconfig, which I typed into PowerShell.

8. Network interface being used on AWS system is the ethernet "eth0" connection interface. Found this with "ifconfig" command.

9. MAC Address: 0e:c0:9c:42:e1:03, Also found with "ifconfig"

10. Hostname: "ip-10-0-0-25", Found using "hostname"

11. IP address: 10.0.0.25, Found with "ifconfig"

12. Subnet mask: 255.255.255.0, Found with "ifconfig"

13. Gateway: 10.0.0.1, Found with "route -n"

14. Public IP address: 34.224.229.96, Found with "curl ipinfo.io"

15. I use the public/elastic IP to access my AWS system.

Part 2:

1. sudo apt install jupyter

2. When running curl localhost:8888, it said "curl: (7) Failed to connect to localhost port 8888: Connection refused".

3.  jupyter notebook --no-browser
[I 02:26:26.983 NotebookApp] Serving notebooks from local directory: /home/ubuntu
[I 02:26:26.983 NotebookApp] 0 active kernels
[I 02:26:26.983 NotebookApp] The Jupyter Notebook is running at:
[I 02:26:26.983 NotebookApp] http://localhost:8888/?token=92ac1ce015a84381d371fa71523184be2c1ba6a3bebf1487
[I 02:26:26.984 NotebookApp] Use Control-C to stop this server and shut down all kernels (twice to skip confirmation).
[C 02:26:26.984 NotebookApp]

    Copy/paste this URL into your browser when you connect for the first time,
    to login with a token:
        http://localhost:8888/?token=92ac1ce015a84381d371fa71523184be2c1ba6a3bebf1487


4. I just opened up another WSL-Ubuntu session for this step.

5. Token: 92ac1ce015a84381d371fa71523184be2c1ba6a3bebf1487

6. The -N flag is the flag that tells the system to not execute any remote commands. This is a way to indicate that you just want to use the ssh connection to forward ports. The -f flag is in here as well, and this is to tell ssh to go to the background just before execution. This is helpful for when the system needs to ask for passwords and passphrases, such as the token that was put in for this exercise. The -i flag that was in this line is used to select the file from which to read the private key contents to get into the VM. -L is used to specify the TCP port connections that are to be forwarded to the given host and port. I found all this information by doing "man ssh".

  The files that are displayed in the browser are the contents of my Ubuntu VM. They are from my AWS system.

Part 3:

1. To install pip, I used: sudo apt install python-pip
   
   To install http with pip, I used: pip install http

2. To do this, I just did python3 -m http.server 4444

3. Command I used: sudo lsof -nP | grep LISTEN

Here is the output:

sshd        850                   root    3u     IPv4              18147      0t0        TCP *:22 (LISTEN)
sshd        850                   root    4u     IPv6              18173      0t0        TCP *:22 (LISTEN)
systemd-r 29930        systemd-resolve   13u     IPv4            3486069      0t0        TCP 127.0.0.53:53 (LISTEN)
python3   30216                 ubuntu    3u     IPv4            3487536      0t0        TCP *:4444 (LISTEN)

4. To find the PID I used lsof -i :4444

Part 4:

1. git add Lab09
   git commit -m "Finished the lab"
   git push

Extra Credit: Exploring Jupyter

To create the jupyter notebook, I used the "localhost" browser session that I pulled up in my browser with port forwarding. On the front page of Jupyter, I clicked on "new" in the right hand corner, and then I clicked "Python 3." Once I created the notebook, I wrote "print('Hello World!')" as the line of code to print "Hello World!" when the notebook is run. After this, I clicked the "run" button and verified the "Hello World" message was printing correctly. Another step I took was I renamed the notebook from the default "Untitled" name to "Hello_World_Extra_Credit_Notebook". To prepare this notebook for any future sharing, I clicked "Cell>All Output>Clear" and "Kernel>Restart & Run All." This is useful for preparing bigger notebooks to be shared, as it makes sure to clear out any "stray" output, and it verifies that the code executes properly.

To put my notebook in my Lab09 folder on GitHub, I first did "git add Lab09", then "git commit -m "Finished Extra Credit"", then "git push"

Extra Credit: Good listening

To make the "echo" part of the message I chose, "Hello World!", I made a script called "portmessage" with an "echo 'Hello World!'" inside of a while loop. Then, I established the listening part of the connection in one terminal connection by running "./portmessage | nc -l 3000". This pipes the output of the script running to the port listening command. As for the port, I chose port 3000 on the local host. After I started running the above command in the first terminal connection, I opened up another connection and typed  "nc localhost 3000" to complete the listening connection using netcat. Once the connection was complete, the second terminal connection started receiving the "Hello World!" messages that were being echoed out. "Hello World!" continued to print until ctrl+c was pressed, or until the process was killed. As for the sources I used, I did use one website I found to figure out how to setup both sides of the listening connection to be able to echo the messages over the port.

Here is the link to the website: https://askubuntu.com/questions/509629/sending-data-to-port-does-not-seem-to-be-working-on-ubuntu-linux

The git commands I used to put my updated changes in GitHub were similar to the ones used in the previous exercise of this lab.

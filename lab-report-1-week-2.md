# Week 2 Lab Report

Welcome, 
This is my Lab report for Week 2 in CSE 15L

Some of the topics we will be covering in this lab report are:

* How to install VSCode
* How to remotely connect to your course specific ieng6 accounts
* Testing out some commands
* Moving files with `scp`
* Setting an SSH Key
* Optimizing remote running<br>

<br><br><br><br><br>





## Installing VSCode

### Lets get started by installing VSCode

<br>
VSCode is immensly useful for a number of different reasons.  
In this lab, we will be using it for its terminal to connect to our ieng6 workstation.  
<br>
<br>
Just to emphasize on how useful VSCode is, I am currently using it to write this website for you and see my updates in real time, but I digress, let get to work!

First step is to navigate to [VSCode](https://code.visualstudio.com/download) and download the version for your operating system.

>If you are unsure what operating system you are using (which would be concerning) then a quick google search will provide steps on how to check.
 
In this report I will be focusing on Mac systems.  OS X with Apple Silicon to be specific.

![Image](https://extraexabyte.github.io/cse15l-lab-reports/VSCode.png)


Once you have downloaded and opened the intallation folder, follow the simple steps to finishing your installation.

### Congratulations!  You have sucessfull installed VSCode  <br> Now lets put it to the test and use it.

<br><br><br><br>
## Remotely Connecting

Now that you have VSCode installed, we can start the fun process of remotely connecting to your course specific ieng6 workstation.

If you are on windows, you will need to install a program called OpenSSH which can be found here: [OpenSSH](https://docs.microsoft.com/en-us/windows-server/administration/openssh/openssh_install_firstuse)

Then, look up your course specific account for this class, CSE15L [here](https://sdacs.ucsd.edu/~icc/index.php)


With all of that completed, we are going to connect using VSCode's remote connect capability.

Start by opening a terminal by clciking the "Terminal" button then "New Terminal"

You should see something like this pop up at the bottom of your window.

![terminal](https://extraexabyte.github.io/cse15l-lab-reports/NewTerminal.png)


Great, now we want to start entering our commands into the terminal.

>```ssh cs15lwi22XXX@ieng6.ucsd.edu```

You will need to replace the XXX just before the @ with your letters for your course specific account.

If you did everything properly, you should see a message that looks like this:

```
⤇ ssh cs15lwi22zz@ieng6.ucsd.edu
The authenticity of host 'ieng6.ucsd.edu (128.54.70.227)' can't be established.
RSA key fingerprint is SHA256:ksruYwhnYH+sySHnHAtLUHngrPEyZTDl/1x99wUQcec.
Are you sure you want to continue connecting (yes/no/[fingerprint])?
```
It is safe to answer 'yes' when you are connecting to a server the first time, but it might be concerning from a security perspective if you see this warning when you connect to a server that you frequently use.

After you type 'yes', you will need to enter your password and press enter to connect.


## Trying some commands

Now that you've sucessfully remotely connected to the ieng6 server, lets try out some commands.

Try entering the following commands:

```ls```

This should list the directories on your machine.

Next,

```ls -a```

will list all directories, including ones that are usually hidden.
![Image](https://extraexabyte.github.io/cse15l-lab-reports/ls.png)


Now that we understand some basic commands, lets use some more


<br><br><br><br>
## Moving files 

As you can imagine, copying and pasting files and text is immensly useful.  It should be no suprise that copying a file from your client to the server would be essential.  This is done with the ```scp``` command which stands for Secure CoPy.

Create a simple java file that prints out "Hi" on your client.  Save the file as WhereAmI and now lets copy it over to our server:
```java
scp WhereAmI.java cs15lwi22agj@ieng6.ucsd.edu:~/
```
![Image](https://extraexabyte.github.io/cse15l-lab-reports/scp.png)

You will be prompted for your password and then the file will be coppied over


## Setting an SSH Key

You may have noticed that it takes a bit of time to enter your password each time you want to SSH or copy a file using ```scp```.

There is a nice way to make logging in easier, that is with SSH keys.  

SSH keys will allow you to store a private key on your computer and a public key on the server.  When you log in, SSH will check the keys and if they match, it will log you in without needing to type your password.

To start, you want to sign out of the machine and be on your computer (client) and then exceute these commands
```
ssh-keygen
```
You will then be propted with: You will want to replace the XXX after Users/ with your user account.
```
Enter file in which to save the key (/Users/XXX/.ssh/id_rsa): /Users/XXX/.ssh/id_rsa
```

You will be asked to create a password but just press enter twice to create an SSH key without a password to avoid issues later down the line.
You will then be told where you key is stored and see a picture of a your SSH key


![SSHKey](https://extraexabyte.github.io/cse15l-lab-reports/Key.png)

Now you want to log into the server again and create a new file to store the key in:

``` $ mkdir .ssh ```

Now sign back out of the server and copy over your key using scp:

```scp /Users/XXX/.ssh/id_rsa.pub cs15lwi22@ieng6.ucsd.edu:~/.ssh/authorized_keys```

Replacing the XXX with your user name that you stored the keys in.  Now you should be able to SSH and SCP into your server without having to enter your password.  If not, retry all of the steps ensuring that the user names are correct and the directories of the keys match.


<br><br><br><br>
## Optimizing Remote Running

Since you will be running a lot of commands on your server and having to switch back and fourth to your client, it helps to do multiple things at once.

A great example would be SSH-ing into our machine, compiling our java program, and running it all in one press of enter.  That can be done by compounding the code like such:
![Photo](https://extraexabyte.github.io/cse15l-lab-reports/command.png)

This will run the three commands all at one.

Another handy trick for optimizing remote running is to utilize the up and down arrow keys to traverse through your command history.

Lastly, try using the tab button when writing common commands such as 

```cd Documents```

That concludes this Lab report.  Thank you for taking your time to read through this and have a great day.


# Program like an Ape today!!


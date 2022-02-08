# Week 6 Lab Report

Time efficiency is a common topic in computer science.

From program runtime-complexity to logging into a remote SSH server, we are focused on shaving off time to improve efficiency and productivity.  SSH-ing into the ieng6 servers is a time consuming task that we have started to optimize using SSH keys, eliminating the need to type your password into the terminal upon each login to ieng6.

Today we will be furthur optimizing the process by using an alias to SSH.  This is not only going to make it quicker to log in, but it will hopefully save you from the frustration of trying to log into the wrong course speciic server.




<br><br><br><br>
## Setting up and Alias

To setup an alias, first we want to navigate to our
>~/.ssh

folder.  There we cant to add a 'config' file as shown below:

![Image](https://extraexabyte.github.io/cse15l-lab-reports/Lab3Screenshots/SSHConfig.png)

<br><br>
We can now log in using our alias:
![Image](https://extraexabyte.github.io/cse15l-lab-reports/Lab3Screenshots/AliasSSH.png)

<br><br><br>
Lastly, this alias can be used for other SSH functions such as SCP to copy files as demonstrated below:
![Image](https://extraexabyte.github.io/cse15l-lab-reports/Lab3Screenshots/SCPAlias.png)
# 21. 'chmod' command (change mode)

This command modifies the read, write and execute(rwx) permissions of a file or directory. 3 sets of users can have their permissions modified; Owner, Group members and Others.

In the immage below, I gave permission to all users to be able to read, write and execute the file sqlite_commands.sh (the permission was initially -rw-rw-rw-- and changed to -rwxrwxrwx-).

![Alt text](<Images/chmod command.png>)



# 22. 'chown' command (change ownership)

This command allows me change the ownership of a file or directory from one user to another. I used this command to switch ownership of the *sqlite_commands.sh* file from the initial owner *nnamdi* to a new user *uzoma*. This change can only be made as a root or superuser.

![Alt text](<Images/chown command.png>)



# 23. 'jobs' command

This command displays a list of running processes and their status. It returns nothing if there are no processes running. Options available are:

jobs -l, list process IDs in addition to the normal information

jobs -n, list only processes that have changed status since the last notification

jobs -p, lists process IDs only

![Alt text](<Images/jobs command.png>)




# 24. 'kill' command

This command is used to manually terminate processes, especially unresponsives ones. You must know the process ID (PID) and the signal to use. Where the signal isn't specified, the default *TERM* signal is sent to terminate the process.

![Alt text](<Images/kill command.png>)

In the image above, I started the firefox browser on the desktop, got its PID (21882) with *pgrep* command. I then ran *kill -9 21882* to kill the process where -9 is the code for kill signal SIGKILL. SIGKILL kills a process forcefully while SIGTERM ( -15) terminates the process while saving its progress.



# 25. 'ping' command

Very commonly used to check that a network or server is reachable. It is also used to troubleshoot connectivity issues.

![Alt text](<Images/ping command.png>)




# 26. 'wget' command

Files are downloaded from the internet using this command. It is non-interactive running in the background without interrupting other processes.

![Alt text](<Images/wget command.png>)



# 27. 'uname' command

This command provides key details about your Linux OS. It is like asking your OS, "who are you and what are you made of?"

![Alt text](<Images/uname command.png>)




# 28. 'top' command

*top* displays information about all processes running on your PC showing a dynamic realtime view of your PC. Its diplay is similar to the running processes display task manager in Windows.

![Alt text](Images/top.png)



# 29. 'history' command

Depending on the Linux shell in use, this command list over 500 previously executed commands. This allows for reuse of commands. You must have sudo priviledges for this to work.

![Alt text](<Images/history command.png>)

![Alt text](<Images/history contd.png>)

The second image above shows that we can also list a number of commands counting buttom-up.




# 30. 'man' command

This displays user manual for commands in Linux. 

![Alt text](<Images/man command.png>)

This is only 17% (39 lines) of the information in the user manual for '**ls**' command.
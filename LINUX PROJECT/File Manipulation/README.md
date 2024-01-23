# Linux Practice Projects

## 1. 'sudo' superuser do command
Allows you perform tasks that require administrative or root permission.
It requires user authentication

![Alt text](<Images/Screenshot 2024-01-15 165617.png>)



## 2. 'pwd' present/current working directory command
This command displays your present working directory. It shows the path to the current working directory using slash (l)

![Alt text](<Images/Screenshot 2024-01-15 173841.png>)



## 3. 'cd' chnage directory command
This command allows users navigate their directories/folders. 

"cd (foldername or path)" e.g cd CommandsLinux or cd /home/nnamdi/CommandsLinux

### Options for cd include cd - and cd --
"cd -" takes you back to the previous directory and 

"cd --" takes you back to the user directory as seen below.

![Alt text](<Images/Screenshot 2024-01-17 105136.png>)



# 4. 'ls' command
list files and directories within a system and it has the ffg. options

ls -R

ls -a

ls -lh

![Alt text](<Images/Screenshot 2024-01-17 114752.png>)

![Alt text](<Images/Screenshot 2024-01-17 115046.png>)



# 5. 'cat' command
This command reads, combines and writes file content on the CLI

It can also be used to merge/concatenate files and their contents. see image below

![Alt text](<Images/Screenshot 2024-01-17 132434.png>)



# 6. 'cp' command
Copy files to and fro directories, ***cp filename directory path***

![Alt text](<cp filestodir.png>)

copy contents of one file to a new file, ***cp source filename destination filename*** (ensure to add the filename extensions e.g .txt) In the shot below, I copied the content of firstfile.txt to a new file i created named fourthfile.txt

![Alt text](<Images/cp filecontent.png>)

copy entire directories, ***cp -R source dir destination dir***
Here I copied the directory commandlist in Linuxcommand directory to Documents.

![Alt text](<cp entiredir.png>)



# 7. mv command:

This is used to **move and rename** files and directories.

![Alt text](<mv files_dirs.png>)

In the image below, I have simply used ***mv current filename new filename*** to rename a file sqlite_commands.sh to sql_commands.sh

![Alt text](<mv rename.png>)




# 8. mkdir command:

This command is used to create new directories. In the image below I used 'mkdir' to create the folder Project_backup and Gitcommands.

The command options "-p" and "-m" are used to create folders in-between existing folders or create folders with permissions.

![Alt text](mkdir.png)


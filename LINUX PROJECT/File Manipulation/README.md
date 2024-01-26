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

The command options "-p" and "-m" are used to create folders in-between existing folders and create folders with permissions respectively.

![Alt text](mkdir.png)



# 9. 'rmdir' command:

This command is used to permanently delete folders/directories. The user must have sudo priviledges in order to use this command.

![Alt text](<Images/rmdir command.png>)



# 10. 'rm' command

Use this command to permanently delete files. The user must have *write* permissions. In the image below, I demonstrated how *rm* command can delete a single file and multiple files. Remember to double check before deleting as this operation cannot be undone.

![Alt text](<Images/rm command.png>)



# 11. 'touch' command:

This command is used to create new files. It is also used to generate and modify a timestamp in the Linux command line.

![Alt text](<Images/touch command.png>)



# 12. 'locate' command:

This command is used to find files in the database system. Using the option **-i** with the 'locate' command will turn of case sensitiity to avoid limitations during search especially when one doesn't remember the exact file name. see image below

![Alt text](<Images/locate command.png>)



# 13. 'find' command:

This command will search for files within a specific directory.

find 
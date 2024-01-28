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

The syntax: find [path] [option] [expression/filename]

In the image below, the path is "/home" the command option is "-name" and the filename is "sql_commands.sh

![Alt text](<find command.png>)

Other options: "find -name filename" (to find a file in the current directory)

![Alt text](<Images/find -name option.png>)

"find ./ -type d -name [directory name]"

![Alt text](<Images/find -type d.png>)



# 14. 'grep' command

This command is used to search for specific word in a file in the current folder. The output will print all the lines containing the word.

![Alt text](<Images/grep command.png>)



# 15. 'df' command

We use df command to report the system's disk usage. This is displayed in percentage (%) and various capacities/sizes in kB, MB or GB

![Alt text](<Images/df command.png>)

other options: df -m displays in MB, df -k dislays the sizes in Kb while df -T displays in Kb and additionally reports the file Types.

![Alt text](<Images/df -m-k-T options.png>)



# 16. 'du' command:

This command will tell you how much space a file or directory takes up on the system. The directory path has to be specified. The example below shows the space taken up by the file named firstfile.txt and the directory Linuxcommands (Note: that there is a folder in named commandlist with 4kb in Linuxcommands)

![Alt text](<Images/du command.png>)

See other du command options in action in the image beloow:

![Alt text](<Images/du options.png>)



# 17. 'head' command:

This command prints out the first 10 line of text in a file.

![Alt text](<Images/head command.png>)

See what other options of 'head' command can do in the image below: 
***head -n prints out specified number of lines*** 
***head -c prints the first number of bytes from the file specified***  
***head -q prints first few lines of multiple files without their headers***
***head -v prints 10 lines of text with the filename as header***

![Alt text](<Images/head -n command.png>)

![Alt text](<Images/head -v command.png>)

![Alt text](<Images/head -c command.png>)

![Alt text](<Images/head -v -q command.png>)



# 18. 'tail' command

This command prints the last 10 lines of text in a specified file. The file state.txt has a list of some states in Nigeria, ***tail state.txt*** prints the last 10 states in the list.

![Alt text](<Images/tail command.png>)

The 'tail' command is a complimentary of the 'head' command. They have the same options -n, -c, -q, -v and -f see some of the commands and theeir output.

![Alt text](<Images/tail options -n -c.png>)




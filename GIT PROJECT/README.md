# 1. Initializing Git Repository

I installed Git on my windows PC and I opened the Terminal **Git Bash** in order to initialize a Git repository.

I am running the following commands to achieve the above: mkdir Devops (to create a directory on my PC named Devops), cd Devops (to change current dir to Devops), git init (to initialize to initialize my repository - main)

![Alt text](<Images/git init.png>)



# 2. Making my First Commit

Here, I created a new file "index.txt" with **touch** command, I tracked the file using the command **git add .** and then commited it to my repository using **git commit -m "initial commit"** see image below.

![Alt text](<Images/git commit.png>)



# 3. Working with Branches

Branches are used to make duplicates of your source codes in order to modify features, make changes and even test the source code before commiting the changes. These changes does not affect the main copy of the code. With Branches different developers can work on one source code simultaneously without recourse to the main copy or themselves.

### My First New Branch

I used the command **git checkout -b Mynewbranch** to create a new branch and switch to it.

![Alt text](<Images/git new branch.png>)


### Listing Branches

**git branch** is the command used to list all the branches in my repository.

![Alt text](<Images/git branch.png>)


### Switching Branches

We can switch from one branch to another using the command **git checkout "branchname"**. I have switched from *Mynewbranch to main*

![Alt text](<Images/git checkout branch.png>)



### Merging Branches

We can merge the content of one branch to another branch. To achieve this, switch to the branch that has the content and then run the command **git merge "requesting branch"**

![Alt text](<Images/git merge.png>)





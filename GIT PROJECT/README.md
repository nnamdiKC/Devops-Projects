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


### Deleting Branches

The command for deleting branches is **git branch -d <branchname>**

![Alt text](<Images/git branch delete.png>)






# Collaboration and Remote Repositories

Git as a version control system can be used any where at anytime. Teams of developers residing any where in the world can use this system to collaborate.

The tool used to achieve this is Github. Git hub is a web based platform where git repositories are hosted. Once your local repositories are hosted on Github, it becomes available either publicly for everyone to access or privately for you alone. All your work stored locally can be *pushed* to Github and vice versa. With this you can track every work on your repositories.

Below is a screen shot of my Github account showing that I have 1 branch (main) and 1 repository (Devops-Projects) containing project directories (Linux practice and Git Projects).

![Alt text](<Images/github account.png>)


### Creating a Repository

I have created a new repository **"Test Projects"**

![Alt text](<Images/github new repo.png>)

![Alt text](<Images/github new repo 2.png>)


### Pushing my Local Git Repository to my Remote Github Repository

![Alt text](<Images/git push to remote.png>)



# Cloning Remote Repositories

A remote repositories can be cloned to allow team members or others make contribution to projects.
The idea of cloning is making an exact copy of a repository on Github to your local machine. The command is **git clone <link to your reomte repository>**



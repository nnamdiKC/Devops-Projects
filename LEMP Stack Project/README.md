# Project 2 - LEMP Stack Implementation
## LEMP Stands for Linux, NGINX, MySQL and PHP.
It is another web stack technology that is used to create websites or web based applications. This project targets proficiency in building dynamic websites with LEMP stack, exploring techniques for handling user requests, interacting with databases, processing forms and implementing robust security measures. It will reveal popular frameworks and tools that can elevate productivity and simplify web application development process.

#### Step 0 - Preparing Prerequisites

I fired up an instance on my AWS account

Using Git Bash, I connected to my server insatance with the following command:

    'ssh -i <Your-private-key.pem> ubuntu@<EC2-Public-IP-address>'

![alt text](<Images/git bash connect to ec2.png>)


#### Step 1 - Installing the Nginx Web Server
Nginx will eable us display web pages to our site visitors. It is a high performance web server.

First, I'll update my Ubuntu server with:

    'sudo apt update'

![alt text](<Images/sudo apt update_nginx.png>)

Then install Nginx server using
    'sudo apt install nginx'

![alt text](<Images/install nginx.png>)

    'sudo systemctl status nginx' will confirm that everything was done properly and that Nginx is up and running

![alt text](<Images/nginx status.png>)

The next thing is to open port 80 on our instance so that I can receive traffic by my web server. I have to edit inbound rule on my ec2 instance to add this option.

TCP port 80 is the default port that web browsers use to access web pages on the internet.

![alt text](<Images/edit inbound rules.png>)

The server is running and can now be accessed locally from the internet.

    Run 'curl http://localhost:80' or 'curl http://127.0.0.1:80'

![alt text](<Images/curl nginx.png>)

Nginx server can also respond to rquest from the internet. Using any browser enter:
    'http://public-address:80'

![alt text](<Images/nginx website.png>)



#### Step 2 - Installing MySQL
As previously seen, Mysql is a database management system (DBMS) that stores and manages data for our website in a relational database.

    'sudo apt install mysql-server' will istall MySQL DBMS

![alt text](<Images/mysql for LEMP.png>)

Log into Mysql database using:
    'sudo mysql'

![alt text](<Images/log into mysql_LEMP.png>)

I will run a security script; preinstalled with MySQL that will over-write some insecure default settings and lock down access to my database system. I will also set a root user password using mysql_native_pasword as default authentication method. The user's password will be **PassWord.1**

    Then exit MySQL using the command 'exit'

![alt text](<Images/secure mysql_LEMP.png>)





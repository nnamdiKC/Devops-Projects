# Project 2 - LEMP Stack Implementation
## LEMP - Linux, NGINX, MySQL and PHP.
It is another web stack technology that is used to create websites or web based applications. This project targets proficiency in building dynamic websites with LEMP stack, exploring techniques for handling user requests, interacting with databases, processing forms and implementing robust security measures. It will reveal popular frameworks and tools that can elevate productivity and simplify web application development process.

### Step 0 - Preparing Prerequisites

I fired up an instance on my AWS account

Using Git Bash, I connected to my server insatance with the following command:

    'ssh -i <Your-private-key.pem> ubuntu@<EC2-Public-IP-address>'

![alt text](<Images/git bash connect to ec2.png>)


### Step 1 - Installing the Nginx Web Server

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



### Step 2 - Installing MySQL

As previously seen, Mysql is a database management system (DBMS) that stores and manages data for our website in a relational database.

    'sudo apt install mysql-server' will istall MySQL DBMS

![alt text](<Images/mysql for LEMP.png>)

Log into Mysql database using:
    'sudo mysql'

![alt text](<Images/log into mysql_LEMP.png>)

I will run a security script; preinstalled with MySQL that will over-write some insecure default settings and lock down access to my database system. I will also set a root user password using mysql_native_pasword as default authentication method. The user's password will be **PassWord.1**

    Then exit MySQL using the command 'exit'

![alt text](<Images/secure mysql_LEMP.png>)

I stated the interactive secure mysql installation script which I used to secure my database. With this I have set a new password on the MEDIUM level of password validation policy for accessing my database.
    'sudo mysql_secure_installation'

![alt text](<Images/secure mysql_LEMP (2).png>)

Let us test the efficacy of the password I have set:

    'sudo mysql -p' #The -p flag is used to prompt for password

![alt text](<Images/sudo mysql -p.png>)

Hurray! It works!

For best practice and increased security, always set up dedicated users with less expansive priviledges for every database especially when hosting multiple databases on your server.

Note: At the time of this writing, the native MySQL PHP library mysqlnd doesn’t support caching_sha2_authentication, the default authentication method for MySQL 8. For that reason, when creating database users for PHP applications on MySQL 8, you’ll need to make sure they’re configured to use mysql_native_password instead. We’ll demonstrate how to do that in Step 6.



### Step 3 - Installing PHP

PHP will process code and generate dynamic content for the web server.

    To get our PHP running properly, I will install:
    1. php-fpm, PHP fastCGI process manager - an external program that Nginx uses to handle PHP processing and acts as a bridge between the PHP interpreter itself and the web server.
    2. php-mysql - a PHP module that allows PHP communicate with MySQL based databases.

Both apps can be installed at once.

    run 'sudo apt install php-fpm php-mysql'

![alt text](<Images/install php-fpm_php-mysql.png>)



### Step 4 - Configuring Nginx to Use PHP Processor




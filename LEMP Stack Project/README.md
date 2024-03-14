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

**Hurray! It works!**

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

Nginx web server allows for creation of server blocks to encapsulate configuration details and host more than one domain on a single server. I am using **projectLEMP** as domain name for this project.

creating the root web directory for my_domain:

    run 'sudo mkdir /var/www/projectLEMP'

![alt text](<Images/mkdir projectLEMP.png>)

Assign ownership of the directory with $USER environment variable to reference the current system user.

    'sudo chown -R $USER:$USER /var/www/prjectLEMP'

![alt text](<Images/chown projectLEMP.png>)

Using *nano*, open a new config file in Nginx **sites-available** directory

    'sudo nano /etc/nginx/sites-available/projectLEMP


Drop the follwoing configuration in the file:

    #/etc/nginx/sites-available/projectLEMP

    server {
        listen 80;
        server_name projectLEMP www.projectLEMP;
        root /var/www/projectLEMP;

        index index.html index.htm index.php;

        location / {
            try_files $uri $uri/ =404;
        }

        location ~ \.php$ {
            include snippets/fastcgi-php.conf;
            fastcgi_pass unix:/var/run/php/php8.1-fpm.sock;
        }

        location ~ /\.ht {
            deny all;
        }

    }

![alt text](<Images/nano projectLEMP.png>)


Activate the configuration by linking to the config file from Nginx's sites-enabled directory:

    'sudo ln -s /etc/nginx/sites-available/projectLEMP /etc/nginx/sites-enabled/'

![alt text](<Images/sudo ln-s projectLEMP.png>)

Test the configuration for syntax errors:

    'sudo nginx -t'

![alt text](<Images/nginx -t.png>)

I will also disable the default Nginx host that is currently configured to listen on port 80.

    run 'sudo unlink /etc/nginx/sites-enabled/default'

Then reload Nginx to apply changes:

    'sudo systemctl reload nginx'

![alt text](<Images/unlink and reload ngnix.png>)

My website is active now. I'll add an index.html file to my web root directory /var/www/projectLEMP and test that the new server block works as expected.

    'sudo echo 'Hello LEMP from hostname' $(curl -s http://169.254.169.254/latest/meta-data/public-hostname) 'with public IP' $(curl -s http://169.254.169.254/latest/meta-data/public-ipv4) > /var/www/projectLEMP/index.html'

![alt text](<Images/add index-html to projectLEMP.png>)

On my browser, **http://public-IP:80** (adding the prot number is optional)

![alt text](<Images/Hello LEMP.png>)

I will get same result as above when I use the DNS in place of public IP as seen below.

![alt text](<Images/Hello LEMP with DNS.png>)




### Step 5 - Testing PHP with Nginx

I can say that at this point, my LEMP Stack is completely installed and fully operational. but I will also test it to validate that Nginx can hand *.php* files off to my PHP processor.

I will do this by creating a PHP file (info.php) in my document root. I will use nano text editor for this.

    'namo /var/www/projectLEMP/info.php'

And add the following lines to the file.

    <?php
    phponfo();

![alt text](<Images/nano info.php_LEMP.png>)

I should be able to access this page on my website with the following url:

    http://myserver_domain_or_IP/info.php

![alt text](<Images/php info page_LEMP.png>)

VOILA! It is working (Y)

NOTE: The information on the PHP page is quite sensitive and so we may want to delete it to avoid unauthorized access to my server. The file can always be regenrated if needed later.

    run 'sudo rm /var/www/projectLEMP/info.php'

![alt text](<Images/rm info.php LEMP.png>)



### Step 6 - Retreiving Data from MySQL Database with PHP

Create a test database with a "Simple To-do List" and configure access to it so that Nginx website will be able to query data from the database and display it.

    Database name: test_database
    Username: test_user

Let us connect to MySQL console using **root** account:

    'sudo mysql -p'
    # -p for password authentication

![alt text](<Images/mysql -p console.png>)

Create the new datadase "test_database"

    'CREATE DATABASE test_database;'

![alt text](<Images/mysql create testdb.png>)

Create a user and grant him full priviledges on the database just created.

    'CREATE USER 'test_user'@'%' IDENTIFIED WITH mysql_native_password BY 'Password@1';'

![alt text](<Images/create new user mysql.png>)

Now let us give the user (test_user) permission over the 'test_database' database. Full priviledges over this database only will be granted to this user but not on other databases on the server.

    'mysql> GRANT ALL ON test_database.* TO 'test_user'@'%';'

![alt text](<Images/grant priviledge mysql.png>)

Exit mysql.

    'exit'

This will return:

    'mysql> exit
    Bye'

Let us test if the user has the proper permissions by login into Mysql using the user's credentials.

    'mysql -u test_user -p'

![alt text](<Images/testing test_user access.png>)

To also confirm that the 'test_user' has access to his database run:

    'mysql> SHOW DATABASES;'

![alt text](<Images/show db for test_user.png>)

COOL!

Let us create a table named **todo_list**.

    'CREATE TABLE test_database.todo_list (item_id INT AUTO_INCREMENT,content VARCHAR(255),PRIMARY KEY(item_id));'

    Output should read:
    'Query OK, 0 rows affected (0.04 sec)do_list (item_id INT AUTO_INCREMENT,content VARCHAR(255),PRIMARY KEY(item_id));'

We can add some rows to our table as well using the command:

    'mysql> INSERT INTO example_database.todo_list (content) VALUES ("My first important item");'

    Output should read:
    'Query OK, 1 row affected (0.01 sec)'

![alt text](<Images/todo_list table.png>)


We can create a PHP script that will connect to MySQL and query for content. Using vi text editor, create a PHP file in the custom web root directory.

    'vi /var/www/projectLEMP/todo_list.php'

![alt text](<Images/todo_list.php file.png>)

Save the script and quit the vi editor.

If this is done properly, we should be able to access our database from our browser using:

    'http://public_domain_or_IP/todo_list.php'

![alt text](<Images/todo_list.php website.png>)

This simply shows that my PHP environment id ready to connect and interact with MySQL server.

WOW! This has been quite interesting.

# Preparing Prerequisites

    1. I created my AWS account
    2. I successfully launched an EC2 instance (ubuntu 22.04)
    3. I was able to connect (ssh) to my EC2 instance from Powershell on my local PC using the PEM file (PBL.pem) I downloaded to my PC from my AWS account. The ssh command is 'ssh -i "PBL.pem" ubuntu@ec2-13-48-1-84.eu-north-1.compute.amazonaws.com'
    4. I tried out some linus commands as well: 'ls -l', 'mkdir', 'touch', used 'vi' to edit a new file and 'cat' to view its content.

![Alt text](<Images/aws_ec2 instance.png>)

![Alt text](<Images/ec2 connect from powershell.png>)



# Installing Apache and Updating the Firewall

#### Step 1 - Install Apache2 and Update the Firewall
    run 'sudo apt update'
![Alt text](<Images/sudo apt update.png>)

    run 'sudo apt install Apache2
![Alt text](<Images/insatll apche2_1.png>)

    Confirm that Apache2 is running: 'sudo systemctl status apache2'
![Alt text](<Images/apache status.png>)


Add an Inbound rule to EC2 configuration to open inbound connection through port 80

![Alt text](<Images/inbound_port 80.png>)

run 'curl http://localhost:80' or 'curl http://127.0.0.1:80' to request Apache HTTP Server on port 80.

![Alt text](Images/curl_localhost.png)

Input "http://(public ip):80" on a web browser to access the Apache web server. The image below shows that the web server is running and is accessible through my firewall.

![Alt text](<Images/pub-ip_80 Apache.png>)



# Installing MySql
#### Step 2 - Install Mysql
Mysql ia a relational database used with PHP. It allows for storage and management of data on our site.

run 'sudo apt install Mysql-server'

![Alt text](<Images/install Mysql.png>)

run 'sudo Mysql' to login to Mysql server as admin user **root**.

![Alt text](Images/login_mysql.png)

Secure access to Mysql server by intorducing a password.

run 'ALTER USER 'root'@'localhost' IDENTIFIED WITH mysql_native_password BY 'PassWord.1';' to define the user password as "PassWord.1"

![Alt text](<Images/define mysql password.png>)

Exit mysql server by typing 'exit' and press enter.

![Alt text](<Images/exit mysql.png>)

run 'sudo mysql_secure_installation' to start the interactive script to enable a password or not.

![Alt text](<Images/mysql secure1.png>)
![Alt text](<Images/mysql secure2.png>)


run 'sudo mysql -p' : the flag -p, to allows for root user password prompt. I entered the password "PassWord.1" to access mysql since i didn't activate the VALIDATE PASSWORD PLUGIN.

![Alt text](<Images/sudo mysql-p.png>)



# Installing PHP
#### Step 3 - Install PHP
I will also istall php-mysql (a module that allows PHP communicate with mysql based database) and libapache2-mod-php ( amodule to enable Apache handle PHP files). All 3 packkages can be installed at once.
run 'sudo apt install php libapache2-mod-php php-mysql' to install the 3 packages.

![Alt text](<Images/install PHP_libapache2_php-mysql.png>)

run 'php -v' to confirm the PHP installation and version.

![Alt text](<Images/php -v.png>)



# Enabling PHP on The Website
#### Step 4 - Creating a Virtual Host for your Website using Apache

Setup a domain called "projectlamp" by creating a directory using command 'mkdir'.
run 'sudo mkdir /var/www/projectlamp'
Also assign ownership to the directory by running 'sudo vi /etc/apache2/sites-available/projectlamp.conf'

![Alt text](<Images/sudo mkdir projectlamp.png>)

Use 'vi' or 'vim' to create and edit the file "projectlamp.conf" in Apache's "sites available" directory.

Run 'sudo vim /etc/apache2/sites-available/projectlamp.conf' and add the follwoing Virtual Host Configuration:

    <VirtualHost *:80>
        ServerName projectlamp
        ServerAlias www.projectlamp 
        ServerAdmin webmaster@localhost
        DocumentRoot /var/www/projectlamp
        ErrorLog ${APACHE_LOG_DIR}/error.log
        CustomLog ${APACHE_LOG_DIR}/access.log combined
    </VirtualHost>

![Alt text](<Images/sudo vim projectlamp.png>)

Run 'sudo ls /etc/apache2/sites-available' to list files and as seen projectlamp.conf is available.

![Alt text](<Images/sudo ls_projectlamp.png>)

Run 'sudo a2ensite projectlamp' to enable the virtual host. "a2ensite" is a script that enables the specified site (in this case, www.projectlamp) contained in the virtual host config file.

![Alt text](<Images/a2ensite projectlamp.png>)

To avoid any conflicts, disable the default site that comes with apache2 installation (000-default). Run the command 'sudo a2dissite 000-default'

![Alt text](<Images/a2dissite 000-default.png>)

Notice that I have realoded Apache2 server using the command **'sudo systemctl reload apache2'** to allow the changes take effect.


Run 'sudo apache2ctl configtest'to ensure your config file doesn't contain syntax errors.

![Alt text](<Images/apache2 configtest.png>)

create a website file index.html in projectlamp directory

'sudo echo 'Hello LAMP from hostname' $ (curl -s http://169.254.169.254/latest/meta-data/public-hostname) 'with public IP' $(curl -s http://169.254.169.254/latest/meta-data/public-ipv4) > /var/www/projectlamp/index.html'

![Alt text](<Images/test website index-html.png>)

Test that the website is working by entering the url in the browser: http://(my-public-ip):80

![Alt text](Images/index_html.png)

You can use the public DNS as well with or without the port will give same output; http://ec2-51-20-95-235.eu-north-1.compute.amazonaws.com

![Alt text](<Images/index-html using pub DNS.png>)



# Creating a Virtual Host for Your Website using Apache
#### Step 5 - Enable PHP on the website

Change the order in which the index.php file is arranged to allow it being the first to be accessed.

![Alt text](<Images/vim dir-conf.png>)

Run 'sudo systemctl reload apache2' to reload Apache2 for changes to take effect

![Alt text](<Images/reload apache2.png>)


Create a PHP file to test that PHP is correctly installed and configured on the server

run 'vim /var/www/projectlamp/index.php' to create and edit index.php

![Alt text](<Images/vim index-php.png>)

After editing and saving the file index.php, refresh the URL and it should display the webpage below:

![Alt text](<Images/index.php page.png>)

After viewing the page, we may need to delete the index.php file as it contains sensitive information about your server and PHP environment.

run 'sudo rm /var/www/projectlamp/index.php' to remove the file.

![Alt text](<Images/rm index-php.png>)

If you refresh the webpage again, it returns to the index.html which is the only file in projectlamp directory and the next file in line in the dir.conf script.

![Alt text](<Images/back to index-html.png>)

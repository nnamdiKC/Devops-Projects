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
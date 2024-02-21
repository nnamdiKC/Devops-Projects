# Preparing Prerequisites

    1. I created my AWS account
    2. I successfully launched an EC2 instance (ubuntu 22.04)
    3. I was able to connect (ssh) to my EC2 instance from Powershell on my local PC using the    PEM file (PBL.pem) I created and downloaded to my PC from my AWS account. The ssh command is  'ssh -i "PBL.pem" ubuntu@ec2-13-48-1-84.eu-north-1.compute.amazonaws.com'
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




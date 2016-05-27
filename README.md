#Linux Server Configuration 

This project is part of the Udacity Fullstack Nanodegree

##Required Components

IP address: 52.33.143.150 
SSH port: 2200

Complete URL to your hosted web application is...
- Amazon EC2 Instance's public URL: http://ec2-52-33-143-150.us-west-2.compute.amazonaws.com/ ...can use this url when configuring third party authentication. 
- http://52.33.143.150/index.html currently works too

##Summary of Software Installed and Configuration Changes Made

1. Created VM with Udacity account, SSH into server

1. Created new user named grader ("sudo adduser grader") and gave permission to sudo ("/etc/sudoers.d", "touch grader", "touch nano", added "grader ALL=(ALL) NOPASSWD:ALL" code using editor)

1. Updated all currently installed packages ("apt-get update", "apt-get upgrade")

1. Changed the SSH port from 22 to 2200 ("nano /etc/ssh/sshd_config", changed port in code number using editor, "service ssh restart", "exit", "ssh -i ~/.ssh/udacity_key.rsa root@52.33.143.150 -p 2200")

1. Configured Uncomplicated Firewall (UFW) to only allow specified incoming connections ("ufw default deny incoming", "ufw default allow outgoing", "ufw allow ssh", "ufw allow http", "ufw allow www", "ufw allow ntp", "ufw allow 2200", "ufw deny 22", "ufw status" to check results)

1. Configured the local timezone to UTC ("dpkg-reconfigure tzdata", selected etc/UTC using menu)

1. Installed and configured Apache to serve a Python mod_wsgi application ("apt-get install apache2", "apt-get install libapache2-mod-wsgi").  Visted 52.33.143.150/index.html to confirm install worked properly.

1. How to install and configure PostgreSQL???

1. How to not allow remote connections???

1. How to create a new user named catalog that has limited permissions to your catalog application database

1. How to install git, clone and setup Catalog App project (from GitHub repository from earlier in the Nanodegree program) so that it functions correctly when visiting server’s IP address in a browser. 

1. 

##List of any 3rd-Party Resources Used to Complete Project
- http://www.2daygeek.com/how-to-change-the-ssh-port-number/#
- http://askubuntu.com/questions/138423/how-do-i-change-my-timezone-to-utc-gmt
- https://www.digitalocean.com/community/tutorials/how-to-deploy-a-flask-application-on-an-ubuntu-vps

##Other Helpful Links
<a href="https://www.udacity.com/account#!/development_environment" target="_blank">Link to Development Environment</a>
<br>
<a href="https://docs.google.com/document/d/1J0gpbuSlcFa2IQScrTIqI6o3dice-9T7v8EDNjJDfUI/pub?embedded=true" target="_blank">Getting Started Guide</a>

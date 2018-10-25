# Linux-Server-Configuration

## Description
  This project uses AWS Lightsail to configure a lunix server to host a web application. My server was configured to specifically host a python flask application using Ubuntu, Apache2, and PostgreSQL. 
  
### IP Address: 
  34.217.82.121
  34.217.82.121.xip.io
### URL:
   http://ec2-34-217-82-121.us-west-2.compute.amazonaws.com
   
## Software
1. You will need an AWS account and a lightsail instance properly set up.
2. You will need to install Apache2, libapache2-mod-wsgi, git (most ubuntu systems already have this) and postgresql on your new server.
    - you can use `$ sudo apt-get update` to check for software updates and then `$ sudo apt-get upgrade` to install the updated software.

## Configurations
1. Configure the ports on your lightsail instance to accept traffic on port 2200 and 123. (This should be done on AWS Lightsail)
2. Create a new user on your server named grader. Give grader sudo rights and create a key-pair to ssh in remotely as grader. 
3. Configure the Firewall on the server to accept traffic on ports 80, 2200, and 123 only. Do not allow traffic on 22. 
4. Clone the application onto the server using git.
5. Configure apache2 and WSGI to host your application. 
6. Configure postgresql to create a database on the server. 

## Troubleshooting
Always start with the apache error log as a guide in troubleshooting `$ sudo cat /var/log/apache2/error.log`
Make sure after any changes to your application on the server you restart apache2 `$ sudo service apache2 restart`
Make sure all modules and packages have been installed properly with `$ sudo apt-get install []` or `$ pip install [package]`
Be sure to check your __init__.py file for the correct database location you created with postgres and if you are initiating a database with a different .py file, be sure to check the location of that database being created. 

For Oauth respectively
  - make sure all instances of the new IP address and URL have been changed in the client_secrets file and the developers console.
  - make sure you are using xip.io to properly create an alias for your IP 

   
## References:
This project would not have been possible without guidance from the following repositories. Anyone searching for in depth instructions to create their own linux configuration should refer to these.
- https://github.com/iliketomatoes/linux_server_configuration
- https://github.com/chuanqin3/udacity-linux-configuration/blob/master/README.md
- https://github.com/mulligan121/Udacity-Linux-Configuration/blob/master/README.md
- https://github.com/SteveWooding/fullstack-nanodegree-linux-server-config


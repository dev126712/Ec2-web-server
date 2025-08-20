# EC2 Web Server with Nginx

## This project demonstrates how to deploy a basic web server on an Amazon EC2 instance. It covers launching the instance, configuring security, installing and managing Nginx, and serving a simple HTML page.


## Launch an EC2 Instance

#### I first launch an ec2 instance with the AMI Amazon Linux 2 and choose the t2.micro free tier instance type.


![Image](https://github.com/dev126712/Ec2-web-server/blob/639c60921edb196a8867d34e516df3bd8a81046b/ec2.png)

## Configuring the Security Group & create the SSH Key

### I created a new ssh key pair to connect to my instance.

### The security group acts as a virtual firewall for the EC2 instance, controlling both inbound and outbound traffic.

### SSH (Port 22) The security groupe allows inbound and outbound traffic on port 22 (SSH) it's crucial for remote access.
#### HTTP (Port 80) The security group also allows traffic on port 80. This rule is crucial for making the web server accessible to the public, allowing users to view the hosted website by entering the instance's public IP address into a web browser.


![Image](https://github.com/dev126712/Ec2-web-server/blob/639c60921edb196a8867d34e516df3bd8a81046b/securityGroup.png)

## Connect to the EC2 Instance, Update the package repo, Install Nginx

### I then connect to my ec2 instance but firt i had to set the correct the permission of my .pem file(ssh key file) by running chmod 400 keypair.pem.
#### I then updated the package repository of my instance to ensure the latest version of software is installed.
### I then install Nginx

![Image](https://github.com/dev126712/Ec2-web-server/blob/639c60921edb196a8867d34e516df3bd8a81046b/ec2Config.png)

## Start and enable Nginx

### I did "sudo systemctl start nginx" to immediately start the Nginx service. It's necessary to get the server up and running right after installation.
### Also "sudo systemctl enable nginx" to configures Nginx to launch automatically every time the system boots. This is crucial for maintaining server uptime without manual intervention after a reboot.
![Image](https://github.com/dev126712/Ec2-web-server/blob/639c60921edb196a8867d34e516df3bd8a81046b/nginx.png)


## Deploy the simple Web Page

### Nginx serves web content from a default directory, which on Amazon Linux 2 is /usr/share/nginx/html/. To deploy the website, I created a index.html file in this path and paste my html code in it. This file serves as the main entry point for the website.

![Image](https://github.com/dev126712/Ec2-web-server/blob/639c60921edb196a8867d34e516df3bd8a81046b/webpage.png)

## Access the Web Server

### After successfully deploying the index.html file, I access the web server by navigating to the ec2 instance's public IP address in my web browser. The security group rule allowing inbound traffic on port 80 makes this connection possible.

![Image](https://github.com/dev126712/Ec2-web-server/blob/639c60921edb196a8867d34e516df3bd8a81046b/webpage1.png)
![Image](https://github.com/dev126712/Ec2-web-server/blob/639c60921edb196a8867d34e516df3bd8a81046b/nginx2.png)

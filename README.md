## EC2 Web Server with Nginx
## In this project, I will deploy a web server using Amazon EC2 instance. I will launch an EC2 instance, install Nginx, and configure it to serve a basic website.

### Launch an EC2 Instance
# I first launch an ec2 instance with the AMI Amazon Linux 2 and choose the t2.micro free tier instance type. I created a new ssh key pair to connect to my instance.


![Image](https://github.com/dev126712/Ec2-web-server/blob/639c60921edb196a8867d34e516df3bd8a81046b/ec2.png)

### Security Group
# The security groupe allows ssh on port 22 to connect to it.
# The security group also allows traffic on port 80 to access the Web Server on my browser.


![Image](https://github.com/dev126712/Ec2-web-server/blob/639c60921edb196a8867d34e516df3bd8a81046b/securityGroup.png)

### Connect to the EC2 Instance, Update the package repo, Install Nginx
# I then connect to my ec2 instance but firt i had to change the permission of the .pem file(ssh key).
# I updated the repo package of my instance.
# I then install Nginx

![Image](https://github.com/dev126712/Ec2-web-server/blob/639c60921edb196a8867d34e516df3bd8a81046b/ec2Config.png)

### Start and enable Nginx
# I did "sudo systemctl start nginx" to immediately start the Nginx service. It's necessary to get the server up and running right after installation.
# Also "sudo systemctl enable nginx" to configures Nginx to launch automatically every time the system boots. This is crucial for maintaining server uptime without manual intervention after a reboot.
![Image](https://github.com/dev126712/Ec2-web-server/blob/639c60921edb196a8867d34e516df3bd8a81046b/nginx.png)
![Image]()

### Deploy the simple Web Page
# I created an index.html file in the /usr/share/nginx/html/index.html file path uses for nginx web file and paste my simple html file.

![Image](https://github.com/dev126712/Ec2-web-server/blob/639c60921edb196a8867d34e516df3bd8a81046b/webpage.png)

### Access the Web Server
# After saving my index.html file, I access it by entering my ec2 instance public address on port 80(http).

![Image](https://github.com/dev126712/Ec2-web-server/blob/639c60921edb196a8867d34e516df3bd8a81046b/webpage1.png)

### Configure Auto Start to Ensure the web server starts on reboot
![Image](https://github.com/dev126712/Ec2-web-server/blob/639c60921edb196a8867d34e516df3bd8a81046b/nginx2.png)

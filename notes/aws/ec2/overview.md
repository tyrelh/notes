# EC2 Overview
* Virtual machines (EC2), storing data (EBS), distributing load across machines (ELB), scaling services (ASG)
* **Elastic IP**: essentially a static IP that you can assign to instances
    * You can only own 5 Elastic IP per account
* When you stop an EC2 instance you will loose its dynamic public IP
* Assigning an Elastic IP to an instance will persist if the instance is stopped
* Running on EC2 via SSH:
```bash
yum update -y # update packages
yum install -y httpd.x86_64 # install httpd
httpd Apache server
systemctl start httpd.service # start server
systemctl enable httpd.service # enable server to start on boot
```
* `httpd` serves files from `/var/www/html/index.html`
* Possible to bootstrap config of instances using **EC2 User Data** script. Will run once at startup
* Useful for:
    * Installing updates
    * Installing software
    * Downloading common files
    * Anything else
* EC2 User Data script runs at boot
* Plain test EC2 User Data script will be base 64 encoded before transmission to the instance

## Pricing
* EC2 instance prices (per hour) vary based on:
    * Region
    * Instance type
    * Launch type
    * OS
* Billed by the second with minimum of 60 seconds
* Also pay for storage, data transfer, public IPs, load balancing
* Do NOT pay for stopped instances, only above
* `( t > 60 ? t : 60 ) * cost`
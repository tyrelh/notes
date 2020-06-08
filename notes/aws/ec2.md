# EC2 - Elastic Compute Cloud

## General
Virtual machines (EC2), Storing data (EBS), Distributing load across machines (ELB), Scaling services (ASG)


## Instance Types
Five distinct characteristics:
* RAM (type, amount, generation)
* CPU (type, make, frequency, generation, cores)
* I/O (disk performance, EBS, optimizations)
* Network (bandwidth, latency)

```
ec2instances.info
```

R, C, P, G, H, X, I, F, Z, CR are specialized in Ram, CPU, I/O, Network, and/or GPU.

M types are balanced.

T2, T3 types are burstable.
* Ok overall CPU performance
* Very good spike CPU performance
* Uses burst credits
* When no credits remain, CPU performance becomes poor
* When no spikes, credits accumulate

T2 Unlimited
* Pay extra if you exceed credit balance but CPU performance remains high


## SSH
**Need to set read-only permissions on credentials pem file for SSH to work with it.**

```shell script
chmod 0400 PemFile.pem
```

Use pem file when SSHing into EC2.

```shell script
ssh -i PemFile.pem ec2-user@<public ip of instance>
```

`ec2-user` is the default user in Amazon Linux.

Use `logout` to exit SSH.


## IP
When you stop an EC2 instance you will loose its dynamic public IP address.

Elastic IP: essentially a static IP that you can assign to instances.

You can only own five Elastic IP per account.

Assigning an Elastic IP to an instance will persist if the instance is stopped.


## Webserver Example
Running a webserver on EC2 via SSH:

```shell script
yum update -y                  # update packages

yum install -y httpd.x86_64    # install httpd Apache server

systemctl start httpd.service  # start server

systemctl enable httpd.service # enable server to start at boot
```

*httpd* serves files from */var/www/html/index.html*.


## EC2 User Data
It's possible to bootstrap config of instances using *EC2 User Data* scripts. Will run once at startup.

Useful for:
* Installing updates
* Installing software
* Downloading common files
* Anything else you would like to do at boot

EC2 User Data scripts run as root.

Plaintext EC2 User Data script will be base64 encoded before transmission to the instance.


## Instance Launch Types
### Overview
* On Demand Instances: short workloads, predictable pricing.
* Reserved Instances: long workloads, > one year.
* Convertible Reserved Instances: long workloads with flexible instance types.
* Scheduled Reserved Instances: launch within a time you reserve.
* Spot Instances: short workloads, for cheap, can loose instances.
* Dedicated Instances: no other customers will share your hardware.
* Dedicated Hosts: book an entire physical server, control instance placement.

### On Demand Instances
Pay for what you use. Billed per second after first minute.

Highest cost but no up front payment.

No long term commitments.

Recommended for short-term and uninterrupted workloads where you can't predict how the app will behave.

### Reserved Instances
Up to 75% discount compared to on-demand.

Pay up front for what you use with long-term commitment.

Reservation period of one year or three years.

Reserve specific instance types.

Recommended for steady-state applications (think databases).

### Convertible Reserved Instances
Can change instance type.

Up to 54% discount over on-demand.

### Scheduled Reserved Instances
Launch within time window you reserve.

For example: every weekend for a sport event.

### Spot Instances
Up to 90% discount over on-demand.

Bid on prices. Prices vary based on demand.

You get 2 minute warning when price exceeds your maximum bid

Good for: batch jobs, data analysis, workloads that are resilient to failures.

### Dedicated Hosts
Physically dedicated EC2 server.

Control of EC2 instance placement.

Visibility into underlying sockets and physical cores of hardware.

Allocated for three year period.

Useful for:
* Software that has complicated licenses (BYOL - bring your own license)
* Strong regulatory compliance

### Dedicated Instance
Running on hardware that is dedicated to you.

No control of hardware.

May share hardware with other instances in your same account.

If you start/stop dedicated instances, they may change hardware.


## Pricing
EC2 instance prices (per hour) vary based on:
* Region
* Instance type
* Launch type
* OS

Billed by the second with minimum of 60 seconds.

Also pay for storage, data transfer, public IPs, load balancing.

Do not pay for stopped instances.

`(t > 60 ? t : 60) * cost`


## AMI: Amazon Machine Image
Different OSs available which you can customize at boot using EC2 user data scripts.

Can make custom AMIs:
* Pre-installed packages
* Faster boot, no need for EC2 user data script
* Monitoring/Enterprise software
* Security concerns
* Control of maintenance and updates
* Active Directory Integration
* Installing your app ahead of time
* Using someone elses AMI

AMIs are built for specific regions. Not global.


## Instance Meta-data
Allows EC2 instances to learn about themselves without using an IAM Role.

The URL is: [http://196.254.196.254/latest/meta-data](http://196.254.196.254/latest/meta-data).

Remember:
* Meta-data: info about the instance
* User data: launch script for the instance

This meta-data is provided with every EC2 instance and doesn't require any particular Role or permissions.


## EC2 Checklist for Exam
* How to SSH into EC2 and change pem file permissions
* How to properly use security groups
* Differences between private, public, and Elastic IPs
* How to use EC2 User Data to customize instance at boot
* That you can build custom AMI to enhance your OS
* EC2 is billed by the second. Can easily be created and thrown away.
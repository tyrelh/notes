# Security Groups
* They **regulate access to ports**, **authorized IP ranges**, **inbound** network, and **outbound** network
* A firewall that lives **outside** of EC2 instance
* Can be attached to multiple instances and instances can have multiple Security Groups
* Locked to region/VPC combination
* **When creating a security group it is bad practice to use 0.0.0.0 as source. Use specific IPs.**
* Good practice to maintain a security group specific for SSH access
* If app/instance is not accessible it is likely a security group issue
* All inbound traffic is blocked by default. All outbound traffic is allowed by default
* Can **reference a security group from another**. For example you could authorize inbound in one security group from another

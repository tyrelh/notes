# EC2 SSH
* **Need to set read-only permissions on credentials pem file for SSH to work with it**
```bash
chmod 0400 pemFile.pem
ssh -i pemFile.pem ec2-user@<public ip>
```
* `ec2-user` is the default user in Amazon Linux
* use `logout` to exit SSH
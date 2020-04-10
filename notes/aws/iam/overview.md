# IAM Overview
* IAM (Identity and Access Management), Users, Groups, Roles
* Policies written in JSON
* Groups contain users. Roles can be used by machines or users
* Users, Groups, and Roles can all have Policies
* IAM is global (across regions)
* It is best to give users the least amount of privledges
* Big enterprises can integrate their own repo of users using their own credentials using the SAML standard (IAM Federation)
* 1 IAM user per person. Do not share users
* 1 IAM role per application
* Never use root account except for initial setup
# IAM - Identity and Access Management

## Overview
Contains Users, Groups, Roles, Policies.

Groups contain Users. Roles can be used by machines or users.

Users, Groups, and Roles can all have policies.

IAM is global (across regions).

Best practice to give users least amount of privileges.

Big enterprises can integrate their own repo of users using their own credentials using the SAML standard (IAM Federation).

One IAM user per person. Do not share credentials with other people or machines.

One IAM role per app.

Never use root account except for initial setup.


## Policies
Policies on Users, Groups, and Roles can be tested using the AWS IAM [Policy Simulator](https://policysim.aws.amazon.com/home/index.jsp?#).
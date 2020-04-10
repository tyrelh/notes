# S3 Bucket Policies
JSON based policies:
* Resources: buckets and objects
* Actions: Set of API to Allow or Deny
* Effect: Allow or Deny
* Principal: The account or user to apply the policy to

Use S3 Bucket Policy to:
* Grant public access to the bucket
* Force objects to be encrypted at upload
* Grant access to another account (Cross Account)

# S3 Security - Other
Networking:
* Supports VPC endpoints (for instances in VPC without www internet)

Logging and Audit:
* S3 access logs can be stored in other S3 bucket
* API calls can be logged in AWS CloudTrail

User Security:
* MFA (multi factor auth) can be required in versioned buckets to delete objects
* Signed URLS: URLs that are valid only for a limited time (ex: premium video service for logged in users)

Example: You can enforce encryption on objects uploaded to a bucket using a policy
* Use policy generator to generate JSON
* Create conditions to test for the `x-amz-server-side-encryption` header is null and is the specific string `AES256`
* Add these conditions to a Deny `s3:PutObject` statement on the bucket/* ARN
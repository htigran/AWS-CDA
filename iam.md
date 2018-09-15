# IAM
## Identitiy Access Management

Essentially, IAM allows you to manage users and their level of access to the AWS Console. It is important to understand IAM and how it works, both for the exam and for administrating a company's AWS account in real life.

* Centralized control of you AWS account
* Shared Access to your AWS account
* Granular Permissions
* Identitiy Federation (including Active Directory, Facebook, Linkedin, etc.)
* Multifactor Authentication (username/password + e.g. google authenticator)
* Temporary access for users/devices and services ()
* allows own password rotation policy
* Integrates with many different AWS services
* Supports PCI DSS Compliance (Payment card industry)

### Concepts
* Users - end users (people)
* Groups - collection of users under one set of permissions
* Roles - applies to resources (not people)
  * delegate access to AWS resources to users, groups or services
* Policies - a JSON document that defines one or more permissions
  * can be applied to users, groups or roles

#### To enable EC2 instance to read files in an S3 bucket
* Create an IAM role with read access to S3 and assign the role to the EC2 instance

#### Notes
* IAM is universal. It does not apply to regions at this time.
* New users have no permissions when created
* New users are assigned Access Key ID & Secret Access Keys 
  * command line and APIs only
  * can't be used to login in to Console
  * Can be viewed once only 

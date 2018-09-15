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

### Web Identity Federation
Web Identitiy Federation lets you give your users access to AWS resources after they have successfully authenticated with a web-based identity provider like Amazon, Facebook, or Google.

Following successful authentication, the user receives an authentication code from the Web ID provider, which they can trade for temporary AWS security credentials.

#### Amazon Cognito
Provides Web Identitiy Federation with the following features:
* Sign-up sign-in your apps
* Access for guest users
* Acts as an Identity Broker between your application and Web ID providers, so you don't need to write any additional code
* Synchronizes user data for multiple devices
* Recommended for all mobile applications AWS services

Cognito brokers between the app and Facebook or Google to provide temporary crenetials which map to an IAM role allowing access to the required resources.

No need for the application to embed or store AWS credentials locally on the device and it gives users a seamless experience across all mobile devices.

[Web Identitiy Federation Exam Tips](exam_tips.md)

#### To enable EC2 instance to read files in an S3 bucket
* Create an IAM role with read access to S3 and assign the role to the EC2 instance

#### Notes
* IAM is universal. It does not apply to regions at this time.
* New users have no permissions when created
* New users are assigned Access Key ID & Secret Access Keys 
  * command line and APIs only
  * can't be used to login in to Console
  * Can be viewed once only 

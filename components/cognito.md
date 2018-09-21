### Web Identity Federation
Web Identitiy Federation lets you give your users access to AWS resources after they have successfully authenticated with a web-based identity provider like Amazon, Facebook, or Google.

Following successful authentication, the user receives an authentication code from the Web ID provider, which they can trade for temporary AWS security credentials.

### Amazon Cognito
Provides Web Identitiy Federation with the following features:
* Sign-up sign-in your apps
* Access for guest users
* Acts as an Identity Broker between your application and Web ID providers, so you don't need to write any additional code
* Synchronizes user data for multiple devices
* Recommended for all mobile applications AWS services

Cognito brokers between the app and Facebook or Google to provide temporary crenetials which map to an IAM role allowing access to the required resources.

No need for the application to embed or store AWS credentials locally on the device and it gives users a seamless experience across all mobile devices.

[Web Identitiy Federation Exam Tips](exam_tips.md)

### Cognito User Pools

User Pools are user directories used to manage sign-up and sign-in functionality for mobile and web applicaitons.

Users can sign-in directly to User Pool, or indirectly via an indentity provider like Facebook, Amazon, or Google. Cognito acts as an Identity Broker between the ID provider and AWS.

Successful authentication generates a number of JSON Web tokens (JWTs).

Identity Pools enable you to create unique identities for your users and authenticate them with identity providers. With an identity, you can obtain temporary, limited-privilege AWS credentials to access other AWS services.

Cognito tracks the association between user identity and the various diffferent devices they sign=in from.

In order to provide a seamless user experience for your application, Cognito uses Push Synchronization to push updates and synchronize user data across multiple devices.

Amazon SNS is used to send a silent push notification to all the devices associated with a given user identity whenever data stored in the cloud changes.

[Cognito Exam Tips](exam_tips.md)

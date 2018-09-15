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


# Exam tips

## Web Identity Federation

* Federation allows users to authenticate with a Web Identity Provider (Google, Facebook, Amazon)
* The user authenticates first with the web ID Provider and receives an authentication token which is exchanged for temporary AWS credentials allowing them to assume an IAM role.
* Cognito is an Identitiy Broker which handles interaction between your applications and the Web ID provider (You don't need to write your own code to do this)
  * Provides sign-up, sign-in, and guest user access
  * Syncs user data for a seamless experience across your devices
  * Cognito is the AWS recommended approach for Web ID Federation particularly for mobile apps
  
## Cognito

* Cognito uses User Pools to manage user sign-up and sign-in directly or via Web Identity Providers(Google, Facebook.)
* Cognito acts as an Identity broker, handling all interaction with Web Identity Providers.
* Cognito uses Push Synchronization to send a silent push notification of user data updates to multiple device types associated with a user ID.

# SNS Simple Notification Service

- sends notifications from the cloud
- fast and fully managed push messaging system
- sends out time critical notifications
- SNS sends push messages, whereas SQS pulls messages
- Topic can be created for notifications to be sent out
- You can create multiple subscriptions for a single topic. Subscription is an endpoint. 
- topic owners can change permissions to allow more than 1 user to publish a topic
- Endpoints can be
  * http, https
  * email, email-json
  * sms
  * amazon sqs
  * application
- Examples of services using SNS
  * Cloudwatch alarm
  * s3 rrs
  * rds notification of change
- can send different messages based on endpoint
- Message data has the following
  * Message
  * MessageId
  * Signature - Base64 encoded SHA1withRSA signature of message, messageid, subject, type, timestamp and topicARN
  * SignatureVersion
  * SigningCertURL
  * Subject
  * Timestamp
  * TopicArn
  * Type
  * UnsubscribeURL

- Confirmation of subscription message stays valid for 3 days
- A notification will not have more than one message
- SNS messages are not guaranteed to be delivered in order
- Message once sent cannot be recalled
- direct addressing is possible, allows delivery to a single endpoint. direct addressing only supported for mobile push, not for sms or email

- SMS notifications
  * Topics with SMS subscription need to have DisplayName; for others it is optional
  * Only first 10 characters of display name will be included in SMS
  * SMS subscriber can stop messages by sending STOP to 30304
  * SMS publications are right now available only in the US east region
  * MMS is not supported
  * SMS restricted to 140 characters including display name
  * Currently only available to US phone numbers

- SNS limits
  * 10 million subscriptions per topic
  * 3000 topics per account
  * SNS message can have upto 256kb of data
  * Billing unit is 64kb

- Mobile push notifications
  * Apple, google, amazon, windows, microsoft and baidu
  * You can specify TTL Time to live for each message, message is deleted after ttl expires. Default TTL is 4 weeks for all mobile platforms
  * TTL = 0 is special case for message to deliver immediately or expire
  * Delivery status feature is available only for mobile push


- Common API
  * AddPermission, RemovePermission

- SNS serive acceepoint URL http://sns.<region>.amazonaws.com

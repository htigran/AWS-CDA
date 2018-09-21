# KMS

## AWS Key Management

AWS Key Managment Service (AWS KMS) is a managed service that makes it easy for you to create and control the encryption keys used to encrypt your data. 
AWS KMS is integrated with other AWS services to make it simple to encrypt your data with encryption keys that you manage.

### The Customer Master Key:
* CMK
  * alias
  * creation date
  * description
  * key state
  * key material (either customer provided or AWS provided)
  
 * Can NEVER be exported
 
 #### Setup a Customer Master Key:
 * Create Alias and Description
 * Choose material option...
  * Use KMS generated key material
  * Your own key material
 * Define Key Administrative Permissions
  * IAM users/roles that can administer (but not use) the key through the KMS API
 * Define Key Usage Permissions
  * IAM users/roles that can use the key to encrypt and decrypt data
  
### KMS API Calls
* aws kms encrypt
* aws kms decrypt
* aws kms re-encrypt (decrypt -> encrypt again)
* aws kms enable-key-rotation

### Envelope Encryption
The Customer Master Key:
* Customer Master Key used to decrypt the data key (envelope key)
* Envelope Key is used to decrypt the data

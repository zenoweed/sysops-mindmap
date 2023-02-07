# CloudTrail 
## Provides governance, compliance and audit for your AWS account 
## Inspect and audit
## A trail can be applied to all regions or a single region 
## Enabled by default 
## Get a history of events/API calls made within your AWS account 
### Console 
### SDK 
### CLI
### AWS services
#### IAM users and roles
## Put logs into
### CloudWatch 
### S3
## If resource is deleted in AWS, check CloudTrail first
## Events
### Management Events
#### Operations performed on your AWS resources 
#### Examples 
##### Configuring security (IAM AttachRolePolicy)
##### Configuring rules for routing data (Amazon EC2 Create subnet)
##### Setting up logging  (AWS CT CreatTrail)
### Data Events 
#### By default, data Events are not logged
##### Because high volume operations
#### Example 
##### S3 object level activity 
###### example 
- GetObject
- DeleteObject
- PutObject
##### Lambda function execution activity (the Invoke) API
### CT Insight Events
#### Enable to detect unusual activity in your account 
##### Inaccurate resource provisioning 
##### hitting service limits 
##### bursts of AWS IAM action 
##### gaps in periodic maintenance activity
#### analyses normal management Events to create a baseline
#### then continuously analyses write events to detect unusual patterns
##### anomalies appear in the CloudTrail console
##### Event is sent to Amazon s3
##### an EventBridge event is generated 
###### for automation needs
## Retention 
### Events are stored for 90 days in CloudTrail 
### to keep events beyond that, log them to S3 and use athena
## Log file integrity validation 
### Digest files
#### References the log files for the last hour and contains a hash of each
#### Stored in the same S3 bucket as the log files
##### different folder
### Helps you determine whether a log file was modified/deleted after CloudTrail delivered it
### Hashing
#### SHA-256
### Digital signing
#### SHA-256 with RSA
### Protect S3 bucket 
#### Bucket policy
#### Versioning
#### MFA Delete
#### Encryption 
#### Object lock
### Protect CloudTrail 
#### IAM
## CloudTrail is not real time
## Integration 
### EventBridge 
#### Used to react to any API call being made in your account 
#### CloudTrail is not real time
##### Delivers an event within 15 minutes of an API call
##### Delivers log files to an S3 bucket every 5 minutes
## Organizations Trail
### Trail logs all events for all AWS accounts in AWS Organization 
### Log events for management and member accounts
### Trail with same name will be created in every AWS account 
#### IAM permissions 
### Member accounts can't remove or modify the organisation trail
#### View only

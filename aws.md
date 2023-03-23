> ## 1 solution to manage AWS WAF rules across multiple AWS accounts, under different OUs
> * AWS Firewall Manager
----------

> ## 26 solution to manage AWS WAF rules across multiple AWS accounts, under different OUs
> * AWS Firewall Manager
----------

> ## 27 popule onlinw game. large number of users. Single AWS Region. S3 bucket stores game assets. DynamoDB stores plater scores. multi-Region solution reduse latency
> * Create another S3 bucket in new Region
----------

> ## 28 establish a patching plan. must be securely
> * User AWS Systems Manager on all instance to mange patching. etst patchs.
----------

> ## 29 maching learing(ML) model by using 600 TB compressed data
> * AWS Snow ball Edge Storage Optimized device
----------

> ## 30 two separate business units. share documents with each other. S3 buckets have millions of objects. security audit identified that all documents must be stoered with encryption. wants to implement server-side S3 encryption keys(SSE-S3)
> * Turn on SSE-S3 on both. User S3 Batch Operations to encrypt
----------

> ## 31 allow employees to work remotely from their homes. using VPN.
> * Create Client VPN endpoint in main AWS account. Configure required routing.
> * not each AWS account !
----------

> ## 32 company developed APIs use API Gateway. After design review, indentifies a set of APIs that do not require public acccess. must design a solution to make set of APIs accessible only from a VPC.
> * Update the API endpoint from Regional to private in API Gateway.
----------

> ## 33 company launched new feature on mobile app. Users can upload hiking and rafting photos and videos anytime.
> * S3 Intelligent Tiering on S3 bucket
----------

> ## 34 data on phsical media. request will be low. Availability and speed  are not concerns.
> * Create S3 bucket. Configure S3 bucket to use S3 Glacire Deep Archive storage as default.
----------

> ## 35 Single AWS Region. serverless application in a single AWS Region. use Amazon SNS topic to push URLs to Amazon SQS. changes produce multi-Region
> * Deploy SQS with Lambda function to other Regions.
> * Subscribe SQS qure in each Region to the SNS topic.
----------


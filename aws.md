> ## 1 company has serveral AWS accounts. implement a least privilege permissions policy allows Lambda functions tun in each of the AWS account
> * centralized account create IAM role has lambda service as trusted entity.
> * other AWS account create IAM role has minimal permissions. Add centralized accounts Lamda IAM role as trusted entity.
----------

> ## 2 site using Application load Balancer(ALB). 24 hours and 8 hours
> * Store the Docker imagesin ECR.
----------

> ## 3 stateless ETL. application is scheduled to run every 4 hours and runs for up to 20 minutes.
> * User AWS Fargate to run. User Amazon EventBridge to invoke Fagete task every 4 hours.
----------

> ## 4 EC2 instance in an Auto Scaling group.
> * Configure scal-in protection
----------

> ## 5 database between 500 GB and 800 GB
> * Create EventBridge rule in the evening. Create second EventBridge rule runs in the morning. invoke another Lambda function that starts instance based on the tag.
----------

> ## 6 Multi-factior authentication (MFA) is required at login. keep traffic on a private network
> * Deploy a landing zone environment
> * create transit gateways and transit getway VPC
> * AWS Single Sign-On
----------

> ## 7 Application Locad Balancer(ALB), with Amazon Elastic Container(Amazon ECS) to process requests. 
> * coom.amazonaws.region.elasticloadbalancing VPC
----------

> ## 8 CIO asked to disign a simple , hghly ...application
> * Amazon SQS queue
----------

> ## 9 application written in NET and MYSQ>. 200,000 daily user.
> * ALB front an EC2 Auto Scaling group
----------

> ## 10 Aurora database credentials to the Lambda function. S3 is for server-side encryption. must not travel across the internet.
> * Enable IAM db auth on Arora DB. Changed IAM role for Lambda funtcion. Deploy a gateway VPC endpoint for Amazon S3
----------

> ## 26 solution to manage AWS WAF rules across multiple AWS accounts, under different OUs
> * AWS Firewall Manager
----------

> ## 27 popular online game. large number of users. Single AWS Region. S3 bucket stores game assets. DynamoDB stores plater scores. multi-Region solution reduse latency
> * Create another S3 bucket in new Region
----------

> ## 28 establish a patching plan. must be securely
> * User AWS Systems Manager on all instance to mange patching.Test patchs.
----------

> ## 29 machine learing(ML) model by using 600 TB compressed data
> * AWS Snowball Edge Storage Optimized device
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

> ## 36 5,000 records set every 15 minutes in plaintext, over HTTPS
> * create AWS Glue crawler   and custom class based on data feed formats
----------

> ## 37 Load for the application is variable, but minimum load and maximum load are known
> * ECR ESC
> * not ECR EKS...
----------

> ## 38 Aurora MySQL separate AWS Region
> * Aurora Replica in defferent Region
----------

> ## 39 
> * 
----------

> ## 40 multiple AWS accounts under same organization. requires the cost to be allocated to the owning project. Project tag. Prevent happening in the future?
> * Create AWS Config rule to find missing tags
> * Ceate SCP to deny action for ec2:Runlnstatance if Project tag is missiing -> not IAM policy
> * Create AWS Config aggregator
----------

> ## 41 company wants to change its internal cloud billing staegy for each business uinits, Use AWS Organizations to manage each business unit.
> * Configure AWS Budgets in the * organization's master account *
----------

> ## 42 failover test caused a 40-second outage. solution to reduce less than 20 seconds
> * RDS Proxy in front of database
> * Migrate db to Amazon Aurora MySQL
> * Ceate Aurora Replica
----------

> ## 43 single 1 Gbps 
> * Provisino Direct Connect gateway
----------

> ## 44 vendor 12 hours to send new license files. uses configuration files with a static IP address
> * store licence files in Amazon S3  => not EC2
> * automation sript to read db server IP address
----------

> ## 45 troubleshoot the issue?
> * Suspend the Auto Scaling group's Terminate process. -> not HealCheck
----------

> ## 46 secure way to allow org1 to access org2?
> * Amazon Resource Name(ARN)
----------

> ## 47
> * 
----------

> ## 48
> * 
----------

> ## 49
> * 
----------

> ## 50 NAT gateway Bytes
> * VPC endpoint policy allows traffic from the application
----------

> ## 51 order-processing platform. VMs, RabbitMQ
> * Create AMI of VM. Amazon MQ. Elastic Kubernetes Service(EKS) to host order-processing
----------

> ## 52 weather maps web app hosted on eu-west-1 Region. S3 with static HTML. use the us-east-1 Region. new users report wather map is slow.
> * create new S3 in us-east-1. Configure S3 cross-region replication to sync from eu-west-1
> * User Lambda@Edge to use S3 bucket in us-east-1 -> NONONO TrasgrerAcceleration endpont
----------

> ## 53 
> * 
----------

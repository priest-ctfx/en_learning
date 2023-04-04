> ## 1 serveral AWS accounts. implement least privilege permissions policy allows Lambda functions tun in each of the AWS account
> * centralized account create IAM role has lambda service (not other accounts) as trusted entity.
> * other AWS account create IAM role has minimal permissions. Add centralized accounts Lamda IAM role (not lambda service) as trusted entity.
----------

> ## 2 site using Application load Balancer(ALB). 24 hours and 8 hours
> * Store the Docker images in ECR.
----------

> ## 3 stateless ETL. application is scheduled to run every 4 hours and runs for up to 20 minutes.
> * Use AWS Fargate to run. User Amazon EventBridge to invoke Fagete task every 4 hours.
----------

> ## 4 EC2 instance in an Auto Scaling group.
> * Configure scal-in protection
----------

> ## 5 database between 500 GB and 800 GB
> * Create EventBridge rule in the evening. Create second EventBridge rule runs in the morning. invoke another Lambda function that starts (NOT restores!) instance based on the tag.
----------

> ## 6（NG） Multi-factior authentication (MFA) is required at login. keep traffic on a private network
> * Deploy a landing zone environment
> * Create transit gateways and transit getway VPC
> * AWS Single Sign-On
----------

> ## 7 Application Locad Balancer(ALB), with Amazon Elastic Container(Amazon ECS) to process requests. 
> * coom.amazonaws.region.elasticloadbalancing VPC
----------

> ## 8 CIO asked to disign a simple , hghly ...application
> * Amazon SQS queue
----------

> ## 9（NG） application written in NET and MYSQL. 200,000 daily user.
> * ALB front an EC2 Auto Scaling group
----------

> ## 10（NG） Aurora database credentials to the Lambda function. S3 is for server-side encryption. must not travel across the internet.
> * Enable IAM db auth on Arora DB. Changed IAM role for Lambda funtcion. Deploy a gateway VPC endpoint for Amazon S3
----------

> ## 11 company does not access data that is more than 1 year old.
> * AWS Glue Data Catalog. data more than 1 year old to S3 Glacier Deep Archive
----------

> ## 12 hundreds of AWS accounts. purchasing new Reserved Instatnces and modifying existing Reserved Instancees.
> * Ensure all AWS account are part of organiztion. with all features enabled.
> * SCP denies es2:PurchaseReservedInstancesOffering
----------

> ## 13 us-east-1 Region IPv4 CIDR block 10.10.0.0/16. us-east-2 Region IPv4 CIDR block 10.10.0.0/24. why error?
> * IPv4 CIDR ranges of two VPCs overlap
> * IAM row in peer accepter account does not have the correct permissions.
----------

> ## 14 large mobile gaming company migrate AWS. reviewing Cost Explorer notices that ... solution that develpers are lanching new Amazon EC2 instance as part of testing
> * Create new IAM policy
----------

> ## 15 Java backend and NoSQL MongoDB to store subscriber data. need to migrate entire to AWS with similar stucture.
> * Configure Amazon DocumentDB with multiple Zones. Deploy EC2 Auto Scaling group accross multiple Availability Zones
> * (there is no on-demand !!!)
----------

> ## 16 company concerned that, if a production CloudFormation statck is deleted, EBS volumes might also be deleted.
> * add DeletionPolicy
----------

> ## 17 MySQL heavy I/O operations
> * Performing a one-time migration
----------

> ## 18 company is required to store the data for 120 days only, after which the data can be deleted.
> * TTL
----------

> ## 19 application team has stored the database credentials as secrets n AWS Secrets Manager
> * role that is named DBA-Secret
----------

> ## 20 static assets S3 bucket hosted in production account. Also uses development account disign team can access. after testing need to load assets into S3 bucket in the production account
> * 2个In the production account选项都选
> * In the Development account, 选有IAM的 并且 结尾有production
----------

> ## 21 PostgreSQL unable to scale due to heavy. already set up a VPN connection between network and AWS.
> * use Amazon Kinesis Data Firehose to buffer events.
> * Elasticsearch Service(Amazon ES) to recive events.
----------

> ## 22(NG) asynchronous HTTP application
> * Lambda function and API Gateway. Route 53 to use a failover router policy
----------

> ## 23 
> * aws:RequestedRegion
> * ec2LInstanceType
----------

> ## 24 
> * AWS Elastic Beanstalk
----------

> ## 25 
> * AWS Schema Conversion Tool
----------

> ## 26 solution to manage AWS WAF rules across multiple AWS accounts, under different OUs
> * AWS Firewall Manager to manage AWS WAF
----------

> ## 27 popular online game. large number of users. Single AWS Region. S3 bucket stores game assets. DynamoDB stores plater scores. multi-Region solution reduse latency
> * Create another S3 bucket in new Region
----------

> ## 28 establish a patching plan. must be securely
> * User AWS Systems Manager on all instance to mange patching.Test patchs.
----------

> ## 29 machine learing(ML) model by using 600 TB compressed data
> * AWS Snowball Edge Storage Optimized device
> * 看到BULK INSERT 不要选！！！
----------

> ## 30 two separate business units. share documents with each other. S3 buckets have millions of objects. security audit identified that all documents must be stoered with encryption. wants to implement server-side S3 encryption keys(SSE-S3)
> * Turn on SSE-S3 on both. Use S3 Batch Operations to copy and encrypt
----------

> ## 31 allow employees to work remotely from their homes. using VPN.
> * Create Client VPN endpoint in main AWS account. Configure required routing. -> not each AWS account !
----------

> ## 32 company developed APIs use API Gateway. After design review, indentifies a set of APIs that do not require public acccess. must design a solution to make set of APIs accessible only from a VPC.
> * Update the API endpoint from Regional to private in API Gateway.
----------

> ## 33 company launched new feature on mobile app. Users can upload hiking and rafting photos and videos anytime.
> * S3 Intelligent Tiering on S3 bucket
----------

> ## 34 data on phsical media. request will be low. Availability and speed  are not concerns.
> * Create S3 bucket. Configure S3 bucket to use S3 Glacier Deep Archive storage as default.
> * S3 Glacire Deep Archive 新型Amazon S3 存储类，长期保存一年内很少访问的数据
----------

> ## 35 Single AWS Region. serverless application in a single AWS Region. use Amazon SNS topic to push URLs to Amazon SQS. changes produce multi-Region
> * Deploy SQS with Lambda function to other Regions.
> * Subscribe SQS qure in each Region to the SNS topic.
> * SQS是消息队列服务。Lambda是一个事件驱动的平台，SQS加了Lambda function函数，就可以扔到Lambda跑了。
----------

> ## 36 5,000 records set every 15 minutes in plaintext, over HTTPS
> * create AWS Glue crawler   and custom class based on data feed formats
> * Glue 爬网程序。当然要根据喂进来的数据格式自定义不同的class
----------

> ## 37 Load for the application is variable, but minimum load and maximum load are known
> * ECR ECS -> not ECR EKS
> * ECR 管理docker注册表
> * ECS 管理容器编排
> * EKS 管理Kubernetes
----------

> ## 38 Aurora MySQL separate AWS Region
> * Aurora Replica in defferent Region
----------

> ## 39 share S3 bucket with strategy team can view the objects
> * Set the principle
> * grant decrypt permission to the stategy_reviewer IAM role -> not encrypt
----------

> ## 40 multiple AWS accounts under same organization. requires the cost to be allocated to the owning project. Project tag. Prevent happening in the future?
> * Create AWS Config rule to find missing tags
> * Ceate SCP to deny action for ec2:Runlnstatance if Project tag is missiing -> not IAM policy
> * Create AWS Config aggregator
> * * SCP是一种组织策略，管理组织中的权限
> * * IAM用于控制对资源的访问权限
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
> * Provision Direct Connect gateway
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

> ## 53 tocentrally-restrict access
> * Review the Access Advisor in AWS IAM to determaine
> * Remove default Fullansaccess SCP -> not Denyawsacess
> * Define Organizatinal Units (OUS)
----------

> ## 54 2 TB
> * Create an Amazon FSx for Windows File Server file system.
----------

> ## 55 electoronic document. web application communicates with Amazon API Gateway Regional endpoints. must impvoe latency outside of Europe
> * Enable S3 Transfer Acceleration on S3 bucket.
> * Change the API Gateway Regional endpoints
----------

> ## 56 must ensure users can regain access.
> * using update-file-system command
----------

> ## 57 
> * why not snow ball????
----------

> ## 58 
> * Create a new customer-managed prefix list. Share the customer-managed prefix list
----------

> ## 59 HR departments is releasing a new system that will lanch in 3 monthes.
> * AWS Billing and Cost managerment console, use the organization's management accoutn to trun off RI shareing for the HR department's prodction AWWS account.
> * NOT use console to trun off RI sharing...
----------

> ## 60 remote plants
> * Use AWS control Tower to create new OUs to add accounts for the * new plants *
----------

> ## 61 remote plants
> * Define Route 53 outbound. Conifgure AWS Resourece Access manager (AWS RAM)
----------

> ## 62 
> * Install the Amazon CloudWatch agent
----------

> ## 63 198.51.100.2 203.0 
> * CouldWatch (not Clud Trail) console ... 198.51.100.2 ... 203.0 
----------

> ## 64 
> * Deploy the security tool
> * Provision a Gateway Load Balancer .... security tool
----------

> ## 65
> * Aurora Replicas robin routing and sickly
----------

> ## 66 
> * Configure AWS OpsWorks for Puppet Enterprise
----------

> ## 67
> * Set the action of the web ACL rules to Count.
----------

> ## 68 给段儿代码
> * kms:GenerateDataKey
----------

> ## 69 
> * FTP server Amazon Simple Notification Service (Amazon SNS)
----------

> ## 81 一段代码
> * 有一堆CRUD的操作选项
> * 选择 Remove the FullAWSAccess SCP
----------

> ## 82
> * my.service.com ... NLB DNS
----------

> ## 83
> * associate the private hosted zone
> * ... Delete association
----------

> ## 84
> * uploaded vidieos in Amazon S3
----------

> ## 85
> * root SCP to the Production
----------

> ## 86
> * (AZs) to the VPC ... failover routing policy and health checks
----------

> ## 87
> * Create an alias for every new deployed version
----------

> ## 88
> * Secrets Manager RoutationSchedule (NOT other tools..), to rotate the database password every 90 days
----------

> ## 89
> * 
----------

> ## 90
> * Register a block in AWS account. Create Elastic IP Address
----------

> ## 91
> * 
----------

> ## 92
> * Create an IAM role with AoazonSSMManaged InstanceCore
----------

> ## 93
> * AWS DataSync to schedule a daily task
----------

> ## 94
> * Enable resource shareing
> * Create Resouce Access Manager.... Organizations OU ... Select each subnet(not prefix) to accociate
----------

> ## 95
> * VmWare vSphere client
----------

> ## 96 pathing process
> * Use System Manager to manage patehces
----------

> ## 97 
> * 
----------

> ## 98 
> * ...SFTP... Update sftp.example.com in Route 53
----------

> ## 99 
> * !!!!
----------

> ## 100 
> * Update IAM policy for the engineers with permissions to only allow AWS CloudFormation actions.
----------

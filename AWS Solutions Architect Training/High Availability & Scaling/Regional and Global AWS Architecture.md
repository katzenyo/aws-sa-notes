
## Global Components

- Global Service Location & Discovery
- Content Delivery (CDN) and optimization
- Global health checks & failover
- DNS Layer ([[Route 53 Fundamentals|Route 53]])
	- DNS is used globally for service discovery, regional based health checks, and request routing
- CDN Layer (CloudFront)
	- Used to cache content globally, as close to end users as possible, in order to improve performance
- Systems architecture: collection of regions comprising a whole

## Regional Components

- Regional entry point
- Regional scaling & resilience
- Application services and components

- Web Tier
	- Regional services
		- Load Balancer, 
	- Load Balancer, API Gateway
	- Entry point for customers
- Compute Tier
	- Provides functionality to Web Tier
	- EC2, Lambda, Containers
- Storage Tier
	- Consumed by Compute Tier services
	- [[Elastic Block Store (EBS) Service Architecture|EBS]], [[Elastic File System (EFS) Architecture|EFS]], [[Simple Storage Service (S3) Basics|S3]]
	- CloudFront will sometimes use S3 directly to cache content
- Database Tier
	- RDS, Aurora, DynamoDB, RedShift
	- Caching layer used to interface with DBs
		- Minimizes read performance against DBs directly
- Application Tier
	- Kinesis, Step Functions, SQS, SNS

![[Pasted image 20230227141201.png]]
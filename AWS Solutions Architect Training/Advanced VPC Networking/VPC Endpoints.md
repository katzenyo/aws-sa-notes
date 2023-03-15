
## Gateway Endpoints

>[!Warning] On the Exam
> - Highly Available (HA) across all AZs in a region by default
> - Not accessible outside the VPC
> - Work by using prefix lists and route tables
> 	- Never require changes to apps

- Provide private access to S3 and DynamoDB
- Prefix List added to route table
	- Uses Gateway Endpoint as a target
- Highly Available (HA) across all AZs in a region by default
	- Regionally resilient
- Can configure Endpoint Policies
	- Used to control what the endpoint can access
	- Ideal for high security VPC
- Regional only
	- Can't access cross-region services
- Prevents leaky buckets
	- S3 buckets can be configured to private only by allowing access only from a specific gateway endpoint
	- Implicitly denies everything else but the bucket

### Architecture

#### Without Gateway Endpoints

![[Pasted image 20230314172202.png]]

#### With Gateway Endpoints

![[Pasted image 20230314172357.png]]

## Interface Endpoints

>[!Warning] On the Exam
> - Supports TCP and IPv4 ONLY
> - Uses DNS and a private IP for interface endpoint
> 	- Use private DNS or endpoint specific DNS
> - Don't use route tables - they use DNS
> - Not HA by design/default
> 	- Requires interface endpoints in every AZ in every VPC

- Provide private access to AWS Public Services
	- Historically, anything *EXCEPT* S3 and DynamoDB
	- S3 is now supported
- Added to specific subnets (an ENI)
	- Not highly available (HA)
	- For HA, add one endpoint to one subnet per AZ used in the VPC
- Network access controlled via Security Groups
- Endpoint Policies
	- Restrict what can be done with the endpoint
- Use PrivateLink
	- Allows external services to inject into the VPC and be given ENIs
- Endpoint provides a NEW service endpoint DNS
- Apps can optionally use
	- Endpoint Regional DNS
	- Endpoint Zonal DNS
	- PrivateDNS overrides the default DNS for services

### Architecture

#### Without Interface Endpoints

![[Pasted image 20230314180509.png]]

#### With Interface Endpoints

![[Pasted image 20230314180619.png]]

#### With Interface Endpoints + PrivateDNS

![[Pasted image 20230314180743.png]]
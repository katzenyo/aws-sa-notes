
- [[AWS Public vs Private Services#AWS Public Zone|Public AWS Service]]
	- Network connectivity with public endpoint
	- Assuming correct permissions and VPC is configured for AWS public access
- Coordinates sending and delivery of messages
- Messages are less than 256KB payloads
- SNS Topics are the base entity of SNS
	- Permissions and configuration
- Publishers sends messages to a Topic
- Topics have Subscribers, which receive messages
	- HTTP, Email (JSON), SQS, Mobile Push, SMS Messages, [[AWS Lambda|Lambda]]
- SNS used across AWS for notifications
	- [[CloudWatch Basics|CloudWatch]] and [[CloudFormation Basics|CloudFormation]]
- Delivery Status
	- HTTP, Lambda, SQS
- Delivery Retries
	- reliable delivery
- HA and Scalable (at the Region level)
- Server Side Encryption (SSE)
- Cross-account via Topic Policy

## Architecture

![[Pasted image 20230308232918.png]]


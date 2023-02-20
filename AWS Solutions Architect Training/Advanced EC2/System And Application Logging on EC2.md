
## Logging on EC2

- [[CloudWatch Basics|CloudWatch]] is for [[CloudWatch Basics#Metrics|metrics]]
- [[CloudWatch Logs]] is for logging
	- Neither can natively capture data inside an instance
	- Requires CloudWatch agent to capture instance data
		- Also requires further configuration and permissions

- CloudWatch Agent requires installation + agent config deployed on instance
- Create [[IAM Roles|IAM Role]] with permissions for CloudWatch Logs
	- Attach to EC2 Instance for CloudWatch logs to capture
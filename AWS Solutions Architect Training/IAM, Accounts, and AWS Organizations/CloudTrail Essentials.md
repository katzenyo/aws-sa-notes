- Logs API actions that affect AWS accts
	- Stopping/starting instance, changing security groups, etc
	- Called **CloudTrail Event**
- 90 days stored by default in Event History
- Enabled by default - no cost for default 90 day history
- 3 types: Management Events, Data Events, Insight Events
- Regional service

>[!Warning] On the Exam
> - Global AWS services (IAM, STS, CloudFront): always log to US East 1
> - CloudTrail is NOT real-time; 15-minute delay for logging

## Management Events

- Provide information about management operations (control plane operations) performed against resources
	- Creating/terminating EC2 instance, creating VPC
- Logged by default

## Data Events

- Contain information about resource operations performed on or in a resource
	- Objects being uploaded to/accessed from S3, Lambda function invoked
- Higher volume than mgmt events

- Trail: Logs events for the AWS region it's created in
	- One-region trail
	- All-region trail
		- Acts as a single trail but for all regions
		- Automatically updated as new regions are added by AWS
		- Must be enabled in order to log Global AWS services (IAM, STS, CloudFront)
	- Can store events indefinitely in an S3 bucket
		- Stored as compressed JSON log files
	- Organizational Trail
		- Create from within management acct of an [[AWS Organizations]]
		- Stores all info for all accounts inside the Organization


- Regional AWS services: log to specific region they're located in
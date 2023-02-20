>[!Abstract] Key Facts & Features
> - [[Cloud Service Models#Infrastructure as a Service (IaaS)|IaaS (Infrastructure as a Service)]] - provides virtual machines/instances
> 	- unit of consumption is the VM/instance
> - Private service by default
> 	- Uses VPC subnetting
> 	- Must be configured for public access
> - AZ (availability zone) resilient
> 	- If AZ fails, instance fails
> - Different sizes, capabilities available
> - On-demand billing, per second or per hour
> - [[Instance Store Volumes|Local host storage]] or [[Elastic Block Store (EBS) Service Architecture|Elastic Block Store EBS)]]

## Instance Lifecycle

- Running
	- Billed for all used underlying resources (CPU, networking, storage, RAM)
- Stopped
	- Billed only for storage used
- Terminated
	- All underlying resources stopped
	- All storage and stored data is deleted

## [[Amazon Machine Images (AMI)|Amazon Machine Image (AMI)]]

>[!Warning] On the Exam
>Not stored in an AMI: Instance settings and network settings

- Permissions
	- Public - everyone allowed
	- Owner - implicit allow
	- Explicit - only specific AWS accounts allowed
- Root volume
- Block device mapping

## Connecting to EC2

- Private and public keys are generated
- Save private key, use it to authenticate via SSH (port 22) to Linux systems
	- With Windows, use private key to auth, then connect via RDP (port 3389) using username/password

## Key Concepts

- Allow you to define configuration of an EC2 instankce in advance
- AMI, Instance Type, Storage & key pair
- Networking & security groups
- Userdata & IAM Role
- Configuration is locked, defined once, not editable after creation
	- Must create a new Launch Configuration to make changes
- Launch Templates provide newer features
	- T2/T3 Unlimited
	- Placement Groups
	- Capacity Reservations
	- Elastic Graphics

## Architecture

- One function: used for Auto Scaling Groups

![[Pasted image 20230227152547.png]]

## Key Concepts

- Allow you to define configuration of an EC2 instankce in advance
- AMI, Instance Type, Storage & key pair
- Networking & security groups
- Userdata & IAM Role
- **LC and LT are both locked, defined once, not modifiable after creation**
	- **Must create a new LC to make changes**
	- LT's support versioning
- Launch Templates 
	- provide newer features (i.e. better than Launch Configurations)
		- T2/T3 Unlimited
		- Placement Groups
		- Capacity Reservations
		- Elastic Graphics
	- Support versioning

## Architecture

- One function: used for Auto Scaling Groups

![[Pasted image 20230227152547.png]]
>[!Warning] On the Exam
> - AMIs are regional
> 	- They only work in the region in which they're created
> 	- Can be used to deploy into all AZs within that same region
> 	- AMIs copied to new regions are new, separate AMIs
> - **AMI Baking**: creating an AMI from a configured instance + app
> - AMI can't be edited
> 	- You must launch instance, update the config, then make a new AMI
> - AMIs can be copied into other regions (including snapshots)
> 	- **This is the only way to migrate an EC2 instance into another AZ**
> - Default permissions are only for your account
> 	- Private permissions
> 		- AMIs are private by default
> 	- Public permissions
> 	- Individual AWS account access
> - Billed for capacity of EBS snapshots in an AMI


- Container of information
	- Do not contain any real data
	- References snapshots from original EBS volumes and original device IDs to provision the same configuration of volumes
- AMI's can be used to launch EC2 instances
- AWS or community-provided AMIs
- Marketplace AMI (can include commercial software)
- AMI is stored in the region, unique ID
	- Each region has its own set of AMIs
	- ex: `ami-0a887e401f7654935`
- Controls permissions (Public, Your Account, or specific accounts)
- Can create an AMI from an extant EC2 instance

## AMI Lifecycle

1. Launch
	1. Use AMI to launch EC2 instance
	2. BOOT /dev/xvda
	3. BOOT /dev/xvdf
2. Configure
	1. Customization for your organization
	2. Specific apps, services, volumes, etc set to business requirements
3. Create Image
	1. Create AMI from configured (customized) AMI
	2. [[EBS Snapshots, Restore, and Fast Snapshot Restore (FSR)|EBS Snapshots]] referenced inside AMI using block device mapping
	3. Block device mapping contains:
		1. ID of snapshot
		2. Block device of original volume
4. Launch
	1. When launching newly configured instance, it will contain the same EBS volume configuration as the original
	2. Snapshots are used to create new EBS volumes in the AZ

![[Pasted image 20230213161943.png]]
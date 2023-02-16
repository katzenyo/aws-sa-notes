>[!Abstract] Overview
> - EC2 Instances are virtual machines (OS + resources)
> - Run on EC2 Hosts (AWS managed hardware)
> - Shared hosts or Dedicated hosts
> 	- Shared are shared with other customers (but instances are isolated from customers)
> 	- Dedicated are just for you
> - **Hosts run in a single AZ**
> 	- **If AZ fails, the host fails, and instances fails**

>[!Warning] On the Exam
> - **EC2 Hosts run on a single AZ**
> - **EC2 is an AZ resilient service**
> - Cannot [[Elastic Block Store (EBS) Service Architecture|connect EBS]] or ENIs in one AZ to an EC2 instance in another AZ
> 	- AZs are isolated, cannot be cross-connected
> - **EC2 instances cannot be migrated between AZs**
> 	- Must [[Amazon Machine Images (AMI)|clone an AMI]] from an instance to a new AZ in order to migrate

- If instance is restarted, it remains on the same host
- If instance is stopped, then started again, it will start on a new host
	- Host will be in same AZ
- Instances are locked into a specific AZ
	- Instances must be copied to a new AZ
- Instances of same type/generation will occupy same host

## Instance Store

- Local storage
- Temporary

## Networking

- Storage Networking
- Data Networking

When instance is provisioned into a subnet, a primary elastic network interface is mapped to a physical hardware on the EC2 host

- Instances can have multiple network interfaces, even in different subnets, as long as they're in the same AZ

## Storage

- Connects to [[Elastic Block Store (EBS) Service Architecture|Elastic Block Store]]
- Cannot reach across different AZs
- **AZ reliance is critical to EC2 and dependent services**

## Use Cases

>[!Warning] On the Exam
> - Traditional OS + App compute
> 	- App requires certain OS, certain runtime, certain config, etc
> - Long-running/persistent compute
> 	- App needs 24/7 operation
> - Server style apps
> - Apps/services that require burst or steady-state load
> - Monolithic app stacks
> 	- Middleware, db, etc
> - Migrated app workloads or Disaster Recovery (DR) environment
> - Default compute service in AWS
> 	- Only move away if in need of a specific service
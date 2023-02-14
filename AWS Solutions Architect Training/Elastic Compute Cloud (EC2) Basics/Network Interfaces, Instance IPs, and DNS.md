
## EC2 Network & DNS Architecture

>[!Warning] On the Exam
> -  Secondary ENI + MAC = licensing
> 	- Secondary ENI can be detached/attached to a new instance, and take its MAC licensing with it
> - Multiple interfaces for multi-homed (subnets) Management & Data
> 	- ENI can be in 2 different subnets, management traffic and data traffic from two different subnets can be sent/received on the same ENI
> - Use multiple ENIs because security groups are attached to ENIs
> - **OS never sees the Public IPv4**
> 	- **Public IPv4 is always configured on the interface**
> 	- IPv6 is always public
> - IPv4 Public IPs are Dynamic
> 	- Stop->Start = new IP address
> 	- Assigning an Elastic IP avoids this
> - Public DNS resolves to the Private IP inside the VPC
> 	- Outside the VPC, the public DNKS resolves to the Public IP
> 	- Allows instance to instance communication in the VPC to never leave the VPC

- EC2 is isolated in one AZ
- Elastic Network Interface, things that are attached directly to them
	- Isolated to the same AZ as the EC2 instance
	- Possess MAC Address
	- Primary IPv4 Private IP
		- doesn't change for the lifecycle of the interface
	- 0 or more secondary IPs
	- 0 or 1 Public IPv4 addresses
		- is allocated a new one when instance is stopped->started
		- public DNS name resolves to the **primary private IPv4 address**
	- 1 elastic IP per private IPv4 address
		- removes the primary public ipv4 address
		- dynamic (non-elastic) IPv4 address cannot be recovered once changed (same as stopping->starting)
	- 0 or more IPv6 addresses
	- Security Groups
		- Attached to interfaces
		- Impacts all IP addresses on the interface it's attached to
	- Per interface, disable source/destination check
		- Traffic will be discarded if it's not sourced from or destined to one of the IP addresses on the interface
		- This setting must be disabled for an EC2 instance to function as a [[Network Address Translation (NAT) and NAT Gateways#NAT Instance vs NAT Gateway|NAT Instance]]
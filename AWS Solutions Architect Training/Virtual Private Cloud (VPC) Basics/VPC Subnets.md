>[!Warning] On the Exam
> - Only one subnet can be in one AZ, but AZs can have multiple subnets
> - Subnet CIDR cannot overlap with other subnets in the VPC

- AZ Resilient
- Subnetwork of a VPC within a specific AZ
	- If AZ fails, subnet fails
- An AZ can have many subnets, but a subnet is only in one AZ
- IPv4 CIDR by default, subset of the VPC CIDR
	- Cannot overlap with other subnets in the VPC
	- Optional IPv6 CIDR (/64 subset of the /56 VPC - 256 addresses)
- Subnets can communicate with other subnets in the same VPC

## Subnet IP Addressing

- 10.16.16.0/20 (10.16.16.0 -> 10.16.31.255)
- Min /28 (16 IP), max /16 (65,536 IP)
- Reserved IP addresses (unusable, 5 in total)
	- Network address (10.16.16.0)
	- Network + 1 (10.16.16.1) - VPC router
	- Network+2 (10.16.16.20) - Reserved for DNS
	- Network+3 (10.16.16.3.) - Reserved for future use
	- Broadcast address (10.16.31.255) - Last IP in subnet

## DHCP Options Set

- Can be created but not edited
- Auto-Assign Public IPv4
- Auto assign Public IPv6
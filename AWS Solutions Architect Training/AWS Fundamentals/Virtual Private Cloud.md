- Used to create private networks within AWS that other private services run from
- Connects AWS private networks to on-prem infra in hybrid environments
- Connects to other cloud platforms in a multi-cloud environment

>[!Abstract] The Basics
> - VPCs are virtual networks within AWS
> - A single VPC belongs to one account and one region; they are regionally-resilient
> - Operate from multiple AZs within a Region
> - Private and isolated from other VPCs, [[AWS Public vs Private Services#AWS Public Zone|public AWS zone]], and public internet by default
> - Two types: Default VPC and Custom VPC
> 	- Only one Default VPC per region
> 	- Many Custom VPCs per region
> - Do not support multicasting

## VPC Basics

- VPCs by default are [[AWS Public vs Private Services#AWS Private Zone|private]], cannot communicate with each other

### VPC Region Resiliency
- Default VPC is assigned a range of IP addresses, the VPC CIDR
	- **Default VPC assigned only one CIDR**, always the same CIDR: 172.31.0.0/16
	- Custom VPCs can have multiple CIDRs
- Each AZ in a Region gets its own Default VPC with a subset of the VPC CIDR
	- Each subnet is assigned a /20 range (e.g. 172.31.0.0/20, 172.31.16.0/20, etc)
	- number of subnets varies based on number of AZs in a Region
	- **Subnets assign public IPv4 addresses**
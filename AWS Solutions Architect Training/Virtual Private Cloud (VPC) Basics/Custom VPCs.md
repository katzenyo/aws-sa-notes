- Regional service - operates in all AZs in the region
- Isolated networks
- Nothing in or out without explicit configuration
	- Negative actions are limited to the specific VPC
- Flexible config - simple or multi-tier
- Hybrid networking - other cloud + on-prem
- Default or Dedicated Tenancy
	- Shared or dedicated hardware
	- Default: can choose per resource
	- Dedicated tenancy: resources *must* be on dedicated
- IPv4 PRivate CIDR blocks & public IPs
- 1 primary private IPv4 CIDR block
- Min /28 (16 IP), max /16 (65,536 IP)
- Optional secondary IPv4 blocks
- Optional single assigned IPv6 /56 CIDR block
	- publicly routable by default

## DNS in a VPC

- Provided by R53
- VPC `Base IP +2` Address
- `enableDnsHostnames` - gives instances DNS names
- `enableDnsSupport` - enables DNS resolution in VPC
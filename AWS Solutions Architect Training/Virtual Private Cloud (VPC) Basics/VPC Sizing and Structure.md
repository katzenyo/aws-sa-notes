
## VPC Considerations

- The size of the VPC
	- Influences how many services can be used
- Are there any networks that can't be used
- Avoid using ranges used by other VPCs, the cloud, on-prem, partners and vendors
- Try to predict the future
- VPC structure - tiers & resiliency (availability) zones
- VPC minimum /28 (16 IPs), maximum of /16 (65536 IPs)
- Personal preference for 10.x.y.z range (10.16.0.0)
- Avoid common IP ranges, helps avoid future conflicts/issues

## IP Ranges to Avoid (For Classroom Scenario)

- 192.168.10.0/24 (254 addresses)
- 10.0.0.0/16 (AWS, 65,534 addresses)
- 172.31.0.0/16 (Azure, 65,534 addresses)
- 192.168.15.0/24 (London office, 254 addresses)
- 192.168.20.0/24 (New York office, 254 addresses)
- 192.168.25.0/24 (Seattle office, 254 addresses)
- 10.128.0.0/9 (Google Cloud, 8,388,606 addresses [10.128.0.0 - 10.255.255.255])

- How many ranges does a business require?
	- Start with # of AWS regions
	- Reserve 2+ networks per region, per account
	- Regions: 3 US, 1 Europe, 1 Australia (5)x2 - Assume 4 accounts
	- Total 40 ranges

## VPC Sizing

- How many subnets needed?
- How many IPs total? How many per subnet?

## VPC Structure

- Three availability zones + one spare, 4 total minimum
	- Means splitting a single VPC into 4 subnets
	- A /16 becomes four /18s
- Start with 4 tiers: web, app, database, and spare
- Each tier needs own subnet in each AZ
	- 16 subnets total, 4 for each tier in each AZ
	- A /16 VPC split into 16 subnets means each tier gets a /20 subnet

## Proposal

- Company could become a large global entity
- Use the 10.6 -> 10.127 range
	- 10.16 (US1)
	- 10.32 (US2)
	- 10.48 (US3)
	- 10.64 (EU)
	- 10.80 (AUS)
- Sixteen /16 networks for each region
	- Each account in each region receives four /16 ranges
	- Four VPCs per region, per account
- /16 per VPC - 3 AZ (+1 spare), 3 Tiers (+1 spare), - 16 subnets
- /16 split into 16 subnets = /20 per subnt (4091 IPs)
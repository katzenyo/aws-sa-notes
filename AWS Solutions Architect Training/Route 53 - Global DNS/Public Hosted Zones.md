>[!Overview] [[Route 53 Fundamentals|Route 53 Basics]]
> - R53 hosted zone
>	- DNS database for a domain (e.g. google.com)
> - Globally resilient (multiple DNS servers)
> - Created via domain registration using Route 53
> 	- Can be created separately
> - [[DNS Record Types|Host DNS records]]
> - Hosted Zones are what DNS references
> 	- Authoritative for a domain (e.g. google.com)

## Public Hosted Zone

- DNS Database (zone file) hosted by Route 53 on Public Name Servers
- Accessible from the public internet & VPCs
- Hosted on 4 Route 53 name servers (NS) specific for the zone
	- Use [[DNS Record Types#Nameserver (NS) Records|NS records]] to point at these nameservers (connect to global DNS)
- Resource Records (RR) are created within the Hosted Zone
- Externally registered domains can point at Route 53 Public Zone

### Architecture

![[Pasted image 20230220161201.png]]

- VPC Instances are already configured (if enabled) with VPC +2 address as their DNS resolver
	- Allows querying of Route 53 public and internet-hosted DNS zones
- Monthly cost for hosting a public hosted zone
	- Small charge for queries made against it
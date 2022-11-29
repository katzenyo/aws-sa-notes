## Global Network

### AWS Regions
- Contain AWS services
- Three main benefits:
	- Geographic separation, provides resilency in disaster situations (isolated fault domain)
	- Geopolitical separation, affected by laws and regulations of AWS Region location
	- Location control - fine tune performance based on customer location

### AWS Edge Locations
- Local distribution points for faster access to services in AWS Regions

### Availability Zones (AZs)
- Every AWS Region provides multiple AZs
- Isolated fault tolerance, resiliency for services across AZs
	- Virtual Private Cloud (VPC) can be used across AZs for resiliency

### Resiliency Levels
- Globally Resilient
	- Services which are replicated globally across multiple AWS Regions
	- E.g. IAM, Route 53
- Region Resilient
	- Services which are replicated across multiple AZs within a Region
- AZ Resilient
	- Services which are resilient to hardware failures in a single AZ
## AWS Private Zone
- Hosts AWS services like [[EC2 Basics|EC2]]
- Located in a [[Virtual Private Cloud|VPC]]
	- VPCs are isolated unless configured otherwise using private networking
	- Accessible from the VBC it's located in
- Can access public internet via Internet Gateway


## AWS Public Zone
- Located in the AWS Public Zone
- Services here always internet accessible (e.g. S3)
- Private services can be given a public IP, 1:1 translation by [[VPC Routing, Internet Gateway, and Bastion Hosts#Internet Gateway (IGW)|Internet Gateway]]
- Anyone can connect, but permissions are required to access the service
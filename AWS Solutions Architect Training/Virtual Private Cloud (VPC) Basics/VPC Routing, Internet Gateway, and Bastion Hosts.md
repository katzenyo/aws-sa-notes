
## VPC Router

- Every VPC has a VPC router - highly available
- In every subnet, a network+1 address
- Routes traffic between subnets
- Controlled by route tables - each subnet has a route table
- a VPC has a Main route table - subnet default

## Route Tables

- Local routes always take priority
- Subnet must have a route table
	- Controls what happens to data when it leave subnets

## Internet Gateway (IGW)

- Region resilient gateway attached to a VPC
	- Will cover all AZs in a region
- 1 VPC = 0 or 1 IGW, 1 IGW = 0 or 1 VPC
- Runs from within the AWS Public Zone
- Gateways traffic between the VPC and the Internet or AWS Public Zone (S3, SQS, SNS, etc)
- Managed - AWS handles performance

### Using an IGW

1. Create IGW
2. Attach IGW to VPC
3. Create custom Route Table
4. Associate Route Table
5. Default Routes -> IGW
6. Subnet allocate IPv4'

### IPv4 Addresses with an IGW

>[!Warning] On the Exam
> - For IPv4, it's not configured in the OS with the public IP address
> - The OS has no knowledge of the public IP address
> - An EC2 instance is configured using the *private* IP address
> - For IPv6, all addresses are natively publicly routeable

- IPv4 Instance
	- Private IP: 10.16.16.20
	- IPv4 public address: 43.250.192.20
		- Never touch actual services in a VPC
- IGW
	- Maintains a record linking private IP to public IP of instance
- Linux Update Server
- Packet
	- Source 10.16.16.20
	- Destination: 1.3.3.7

## Bastion Host/Jumpbox

- Bastion host = jumpbox
- An instance in a public subnet
- Incoming management connections arrive there
- Used as a mgmt/entry point for private VPCs
	- Often the only way into a private VPC
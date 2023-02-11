- Process of granting a private resource outbound access to the Internet
- NAT Gateway: the AWS version that's available within a VPC

## What is NAT?

- Network Address Translation (NAT)
- Set of processes: remapping SRC or DST IPs
- **IP Masquerading**: hides CIDR blocks behind one IP
	- Required because IPv4 is being exhausted
- Gives Private CIDR range **outbound** internet access

## NAT Architecture

![[Pasted image 20230209171423.png]]

## NAT Gateways

- Runs from a **public subnet**
	- Requires internet gateway, subnets configured to provide public addresses, and default routes to point at the gateway
- Uses Elastic IPs (static IPv4 public)
	- Allocated to a region until deallocated
- AZ-resilient service (HA in that AZ)
	- For region-resilience, deploy NATGW in each AZ
	- Route table for each AZ with the NATGW as a target
- Expensive if using many AZs
- Managed service, scales to 45Gbps
	- Split heavy consumers across two subnets in the same AZ
	- Have two NAT gateways in the same AZ
	- Route each subnet to different NAT gateway to double bandwidth
- billed for duration & data volume
	- 4 cents per hour (partial hours billed as full)
	- 4 cents per GB of processed data

## VPC Design - NATGW Full Resilience

>[!Warning] On the Exam
> - Exam has claimed that one NAT gateway is enough - that it's regionally-resilient - but that is false

![[Pasted image 20230209172255.png]]

## NAT Instance vs NAT Gateway

>[!Warning] On the Exam
> - Must provision multiple NAT Gateways across all AZs for HA
> - NAT Gateway cannot be used as a bastion host, cannot do port forwarding
> - NAT Gateways don't support security groups, supports only NACLs
> - NAT Gateways don't work with IPv6
> - NAT Instances are just EC2 instances

- Disable **source/destination** checks to run a NAT instance
- Use NAT gateways for availability, bandwidth, low maintenance, high performance
	- Default for answering exam questions
	- Highly available within one AZ (auto scales)
	- Not free tier available
	- Don't support security groups, supports only NACLs
- NAT instance: limited by the instance it's running on
	- Fails if hardware fails, storage fails, or AZ fails
	- Multipurpose as bastion hosts, port forwarding to instance inside VPC, flexibility

## What about IPv6?

- NAT is not required because lots of addresses are available
- All IPv6 addresses are publicly routable
- Internet Gateway works with all IPv6 IPs directly
- NAT Gateways don't work with IPv6
- ::/0 route + IGW for bi-directional connectivity
- ::/0 Route + egress-only internet gateway: outgoing access only
>[!Warning] On the Exam
> - Full HA (if designed and implemented correctly)
> - Speed cap (**1.25Gbps**)
> - Latency
> 	- inconsistent # of hops, public internet
> - Cost
> 	- AWS hourly cost
> 	- GB out cost
> 	- Data cap (on prem)
> - Fast to setup
> 	- Hours or less, since all software-based config
> - Can be used as backup for or with Direct Connect (DX)

- Logical connections between a VPC and an on-prem network
	- Encrypted using [[IPSec VPN Fundamentals|IPSec]]
	- Runs over the public internet
- Quick to provision
	- Less than an hour
- Virtual Private Gateway (VGW)
- Customer Gateway (CGW)
- VPN connection between VGW and CGW

## Architecture

### Partially Available

![[Pasted image 20230315175641.png]]

### Highly Available

![[Pasted image 20230315175847.png]]

## Static vs Dynamic VPN (BGP)

![[Pasted image 20230315180059.png]]


>[!Warning] On the Exam
> - DX locations are not owned by AWS
> 	- They are large, regional datacenters where AWS rents space/equipment
> - If you don't have space/hardware at a DX location, comms providers can extend the DX port into business prem
> - **Traffic is not encrypted by default**
> 	- Traffic can be encrypted by using a [[AWS Site-to-Site VPN|site-to-site VPN over the public VIF (virtual interface)]]
> - Ideal for:
> 	- situations where low latency and high speeds are necessary

- Physical connection into an AWS region (1, 10, or 100 Gbps)
- Business premises -> DX location -> AWS region
- DX is simply a dedicated port allocation at a DX location
- Port hourly cost & outbound data transfer costs
- Provisioning time
	- Physical cables, no resilience
- Low, consistent latency and high speeds
- Used to access AWS private services (VPCs) and AWS public services
	- Cannot access the internet

## Architecture
- VIF = Virtual Interface

![[Pasted image 20230316105100.png]]
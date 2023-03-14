
## Key Concepts

>[!Warning] On the Exam
> - Connections enter at the edge
> 	- Connections use AnyCast IPs
> - Transits over AWS backbone to 1+ locations
> - Can be used for non-HTTP/S
> 	- Uses TCP/UDP
> - Differences from CloudFront
> 	- GA doesn't cache content/data
> 	- Doesn't use HTTP/S
> 	- CloudFront does the above
> 	- Global Accelerator is simply network optimization, not content delivery

- Moves the AWS network closer to customers

## The Problem

- Users making connections from farther away (e.g. with globally popular apps)
- More hops creates more issues/latency

## Global Accelerator

- 2x anycast IP addresses
	- 1.2.3.4 & 4.3.2.1
	- Allow a single IP to be in multiple locations
		- Routing moves traffic to closest location
- Traffic initially uses public internet & enters a Global Accelerator edge location
- Data transits globally across AWS global backbone network
	- Less hops, directly under AWS control, better performance
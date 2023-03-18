
- Shield Standard & Shield Advanced (provide DDOS protection)
	- Standard
		- Free
	- Advanced
		- Commercial product, costs money
- Network Volumetric attacks (layer 3)
	- Saturate capacity
- Network Protocol attacks (layer 4)
	- TCP SYN flood
	- Leaves connections open and prevents new ones
	- L4 can also be combined with volumetric attacks
- Application Layer (Layer 7) attacks
	- Web request floods
	- `query.php?search=all_the_cat_images_ever`

## AWS Shield Standard

- Free for AWS customers
	- Protection at the perimeter
	- Region/VPC or the AWS edge
- Common [[Network Starter Pack#Layer 3 - Network Layer|network (layer 3)]] or [[Network Starter Pack#Layer 4 - Transport|transport (layer 4) layer]] attacks
- Best protection using [[Route 53 Fundamentals|R53]], [[CloudFront Architecture|CloudFront]], [[AWS Global Accelerator]]

## AWS Shield Advanced

- $3,000 per month, per org
	- 1 year lock-in + data out per month
- Protects same as Shield Standard but includes anything associated with Elastic IPs (such as EC2), [[Application Load Balancing (ALB) vs Network Load Balancing (NLB)#Application Load Balancers (ALB)|ALBs]], CLBs, and [[Application Load Balancing (ALB) vs Network Load Balancing (NLB)#Network Load Balancer (NLB)|NLBs]]
- Not automatically enabled
	- Must be explicitly enabled in Shield Advanced or AWS Firewall Manager Shield Advanced Policy
- Cost protection (such as EC2 scaling) for unmitigated attacks
- Proactive Engagement & AWS Shield Response Team (SRT)

### Features

- [[Web Application Firewall (WAF)|WAF]] Integration
- Application (Layer 7) DDOS protection (relies on WAF)
- Real time visibility of DDOS events and attacks
- Health-based detection
	- Application specific health checks, used by proactive engagement team
- Protection Groups

> [!Warning] On the Exam
>  - Determine if an ELB should be internet facing or internal only
> 	 - Determines the IP addressing for the ELB nodes
> 	 - If internet facing, nodes are given public IPv4 addresses
> 		 - Can communicate with both public and private instances
> 	 - If internal, nodes are given private IPs only
> 		 - Can communicate only with private instances
> 	 - EC2 doesn't need to be public to work with an ELB
> - Requires 8+ free IPs per subnet and a /27 subnet to allow scaling
> 	- If a question mentions a /28 subnet but not a /27 for scaling space, then /28 is likely the correct answer since it still provides the 8 min required addresses the ELB needs
> - ELB is a DNS A record pointing at 1+ nodes per AZ
> - Nodes (in one subnet per AZ) can scale
> - Listener Configuration controls what the LB does

- Load Balancer: accepts connections from users, then distributes them to backend services
- Configured to run in 2+ AZ's
	- Nodes
		- One or more nodes are placed into a subnet in each AZ and scale with load
		- If one node fails, it's replaced
		- If load increases, additional nodes are provisioned
		- Configured with listeners which accept traffic on a port & protocol and communicate with targets on a port & protocol
		- Internet-facing nodes can access both public & private EC2 instances
- Each ELB is configured with an [[DNS Record Types#A & AAAA Records|A record]] DNS name
	- Resolves to the individual ELB nodes
- ELBs need 8 or more available IP addresses in order to function
	- Also need a /27 or larger subnet (32-5 reserved AWS addresses = 27 addresses) to allow for scale
- Internal ELBs (private only) used to separate different tiers of apps
	- Allows user-facing web server to connect directly to internal app server on user's behalf
	- Allows independent scaling of tiers

## Cross-Zone Load Balancing

- Allows ELB nodes to distribute incoming load equally across all instances across all AZs
	- Enabled by default

![[Pasted image 20230227143356.png]]


>[!Warning] On the Exam
> - NACLs filter traffic crossing the subnet boundary inbound or outbound
> -  Connections within a subnet are not affected by NACLs
> - Rules processed in order
> 	- Lowest rule number first
> 	- Processing stops when a match occurs
> 	- `*` is an implicit deny if nothing else matches
> - Stateless: rules required for requests and responses (1 inboud, 1 outbound)

>[!Abstract] Overview
> - Stateless - request and response are different
> - Only impacts data crossing subnet boundary
> - NACLs can explicitly allow and explicitly deny
> - IPs/CIDR, ports & protocols - no logical resources
> - NACLs cannot be assigned to AWS resources - only subnets
> - Use together with security groups to add explicity deny (Bad IPs/networks)
> - Each subnet can have one NACL (default or custom)
> - A NACL can be associated with many subnets (many-to-one)

- NACLs are stateless
- Rule-pairs are needed on each NACL for each communication type which occurs:
	- Within a VPC
	- To a VPC
	- From a VPC
- VPC is created with a default NACL
- Inbound and outbound rules have implicit deny and an allow all rule
- Custom NACLs are associated with no subnets
	- All traffic denied by default
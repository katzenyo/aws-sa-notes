- CloudFormation is about efficiency
	- Operations performed in parallel (CRUD)
	- Tries to determine a dependency order (VPC -> Subnet -> EC2)
	- References or functions to create these
- DependsOn lets you explicitly define dependency orders
	- e.g. if Resources Y and Z depend on resource A being provisioned, both will wait for A to complete before provisioning

![[Pasted image 20230319154912.png]]
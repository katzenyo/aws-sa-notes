
- CloudFormation Template
	- YAML or JSON
	- Contains logical resources (the what)
		- Creates physical resources based off the logical resources
	- Templates used to create Stacks
		- Can create 1, 20, or 100 stacks in each region
- If stack's template is changed, the physical resources are changed
- If a stack itself is deleted, the physical resources are also deleted (in most cases)
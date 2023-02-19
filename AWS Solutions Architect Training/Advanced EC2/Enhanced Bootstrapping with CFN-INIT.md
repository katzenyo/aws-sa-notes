
- cfn-init
	- helper script installed on EC2 OS
- Simple config management system
- Procedural (User Data) vs Desired State (cfn-init)
- Can install packages, setup groups, users, sources, files, commands, and services
- Provided with directives via metadata and AWS::CloudFormation::Init on a CFN resource

## cfn-init architecture

![[Pasted image 20230218211220.png]]

## CreationPolicy and Signals

- CreationPolicy
	- informs success/fail status of UserData metadata

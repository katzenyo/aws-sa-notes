- Configuration management system
- Config directives stored in a CloudFormation template
- `AWS:L:CloudFormation::Init` - part of a logical resource
- Procedural (how)
- CloudFormation is desired state (what)
- cfn-init
	- helper script
	- installed on EC2 OS

## Architecture

![[Pasted image 20230320153703.png]]

- Important logs:
	- /var/log/cfn-init-cmd.log
	- /var/log/cfn-init.log
	- /var/log/cloud-init.log
	- /var/log/cloud-init-output.log
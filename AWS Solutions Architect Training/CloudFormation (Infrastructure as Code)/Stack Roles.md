
>[!Warning] On the Exam
> - CloudFormation uses permissions of the logged in identity
> 	- Means you need permissions for AWS
> 	- Identity creating the stack doesn't need direct resource permissions, only the PassRole permission

- Allows cloudformation to assume a role to gain permissions
	- Allows role separation

## Architecture

![[Pasted image 20230320140053.png]]
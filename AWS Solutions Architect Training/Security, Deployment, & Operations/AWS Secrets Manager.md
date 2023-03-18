>[!Warning] On the Exam
> - Designed for secrets specifically
> 	- Passwords, API keys, etc
> - Uses Lambda to automatically rotate secrets
> 	- Requires permissions from an [[IAM Roles|execution role]]
> - Directly integrates with certain AWS products
> 	- RDS is one
> - Secured using KMS
> - Look out for questions mentioning secrets, rotation, or RDS, then Secrets Manager is likely correct answer

- Shares functionality with [[AWS Systems Manager Parameter Store]]
- Usable via Console, CLI, API, or SDK's (integration)

## Architecture

![[Pasted image 20230318124138.png]]
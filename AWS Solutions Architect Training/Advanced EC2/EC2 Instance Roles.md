>[!Important] Important
>Instance Roles should always be used rather than adding access into an instance
>Long term credentials (e.g. access keys) should not be stored on instances

- [[IAM Roles]]
	- [[IAM Roles#Policies|Permissions policy]] attached to role 
- InstanceProfile
	- Wrapper around an IAM Role
	- Allows permissions inside an instance
	- Is attached to EC2 instance - not Instance Roles
- Temporary credentials delivered via instance metadata
- Metadata: `iam/security-credentials/role-name`
- Credentials are always rotated and always valid
- CLI tools will use ROLE credentials automatically
- Used for granting AWS services access to other AWS services
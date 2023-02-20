>[!Definition] Role
>A role is one of two types of identities which exists inside an AWS account
> - Best use case for authentication for an unknown number of or multiple principals
> - Best used on a temporary basis
> - Represents a level of access inside a specific AWS account
> - Can be referenced within resource policies
> - Used within AWS Organizations to login to one account in the Organization and access different accounts without having to login again

>[!Definition] Principal
>A physical person, application, device, or process that wants to authenticate with AWS

## Policies

- Two types of policies available for IAM Roles
	- Trust Policy
		- Controls which identities can assume the Role
		- Can reference identities across multiple AWS accounts
		- Allows for anonymous usage
	- Permissions Policy
		- If the Permissions Policy is changed, the permissions of the temporary security credentials also change

## Temporary Security Credentials

- If a Role is assumed by something that's allowed to assume the Role, AWS generates temporary security credentials
- Behave like time-limited access keys
	- Time can be renewed by re-assuming the Role, which generates new credentials
- Can access whatever permissions are specified within the Permissions Policy
- Generated by the Secure Token Service
	- `sts:AssumeRole`

# When to Use IAM Roles

- Lambda Execution Roles
	- Contains a trust policy to trust Lambda service
	- Contains a Permissions Policy to grant access to AWS products/services
	- Lambda assumes the Role when function is executed
		- When function executes, it uses `sts:AssumeRole` operation
	- Lambda is an example of multiple/uncertain number of principles for Roles

- Identity Federation
	- Granting external accounts permissions to access AWS services

- Web Identity Federation
	- Supports 100,000,000s of potential users via Roles

- Cross Account Access

# Service-Linked Roles

- IAM Role linked to a specific AWS service
- Predefined by a service
	- Provides permissions that a service needs to interact with other AWS services on your behalf
- Service might create/delete the role or allow you to do so during setup or within IAM
- Role cannot be deleted until it's no longer required

- Service-linked roles have varying formats and are case-sensitive

- PassRole Permissions
	- `iam:Passrole`
>[!Important]
> IAM is a globally resilient service - any data is always secure across all AWS regions

- Every AWS Account comes with its own copy of IAM - its own database.
- AWS Account has full trust in its instance of IAM
- Three main components:
	- IDP (Identity provider)
	- Authentication process (challenge to prove you are who you say you are)
	- Authorization
- No cost
- Global service/global resilience
- Can allow/deny identites on its AWS Account
- No direct control on external accounts or users
- Supports identity federation (SSO) and [[Multifactor Authentication (MFA)|MFA]]

#### Users
- Identites which represent humans or applications that need access to the account

#### Groups
- Collection of related users (Dev, Finance, HR, etc)

#### Roles
- Can be used by AWS services or for granting external access to the AWS Account
- Example: if you want to grant all EC2 instances access to S3, you'd create a role to accomplish this

### [[IAM Identity Policies|IAM Policies]]
>[!Definition] IAM Policies
>Objects/documents that can be used to allow/deny access to AWS services only when they're attached to Users, Groups, or Roles
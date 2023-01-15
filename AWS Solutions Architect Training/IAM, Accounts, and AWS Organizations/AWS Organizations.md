>[!Definition]
>Allows larger businesses to manage multiple AWS accounts in a cost-effective way with little management overhead.

- Management Account (Master Account, Payer Account)
	- The AWS account used to initialize the AWS Organization
- Heirarchical structure (inverted tree)
	- Organization Root Container
		- Container for AWS Accounts
	- Organizational Units (OU)
		- Contains AWS Accounts or other OUs
- Consolidated Billing
	- Payer Account
		- Individual AWS account billing is passed through to the Management Account
	- Billed monthly, contains all account's billable usage
	- Consolidated reservations and volume discounts across all accounts
- Service Control Policies (SCPs)
	- Restricts individual AWS accounts within the Organization
- IAM
	- IAM users are not required in every individual AWS account
	- IAM Roles can be used to allow IAM users to access other AWS accounts
	- Best practice: have a single AWS account that contains all identities to be logged into
		- Also allow federation with on-prem IDP (Active Directory, OpenLDAP, Okta, JumpCloud, etc)
	- Role switch
		- role switch from federation account (pass-through account) to other member accounts inside the Organization
		- Assumes roles in other AWS accounts
		- Accounts created in the organization can automatically role switch, invited accounts must be manually added
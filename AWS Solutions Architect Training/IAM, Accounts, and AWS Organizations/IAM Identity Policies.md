>[!Abstract] The Basics
>- Policies that get attached to identities inside AWS
>	- Identites: IAM users, IAM groups, IAM roles
>	- Policies: also known as policy documents (JSON)
>- A set of security statements to AWS
>- Grants/denies access to AWS products/features to any identity using the policy
>- AWS Accounts have no access to any AWS resources, except for the Account Root User

## IAM Policy Document

- JSON file that includes one or more statements in a statement block
- Identity needs to prove who it is to AWS - this is called authentication

### Statement structure
- Statement ID/SID: optional field, identifies a statement and what it does
	- Best practice to use SIDs regardless of the size of a policy document
- Every interaction with AWS is two things: resource you're interacting with, and actions to perform on the resource
	- Statements only apply if the interaction with AWS matches the action and resource
	- Three options for actions: specific individual action, wildcards, and a list of multiple specific actions
	- Use ARN (Amazon Resource Name) format for specific resources
- Effect: what the operation does if the action and resource match the operation

### Overlapping Policies

- Priorities, in order
	1. Explicit DENY
		1. Overrules all other effects, always takes priority over all others
	2. Explicit ALLOW
		1. Take effect unless an explicit deny also exists
	3. Default DENY (implicit)

## Inline Policies

- JSON policies that are applied individually to each account
	- e.g. a separate but identitical policies

## Managed Policies

- Reusable, single policy can be attached to multiple accounts
- Should be used for normal, default operational rights]
	- e.g. a set of common access rights to grant to multiple people
- Low management overhead (changes immediately impact accounts they're attached to)
- Two main types
	- AWS managed policies
		- Created and managed by AWS
	- Custom managed policies, can be created and customized as needed
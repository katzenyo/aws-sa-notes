

- Deploy stacks across many accounts & regions
- StackSets are containers in an admin account
	- They contain stack instances, which reference stacks
- Stack instances & stacks are in target accounts
	- Target accounts are where resources are deployed
- Each stack = 1 region in 1 account
- Security: self-managed or service managed

## Architecture

![[Pasted image 20230320132349.png]]

## Definitions

- Concurrent Accounts: defines # of individual AWS accounts used at the same time
- Failure Tolerance: # of deployments that can fail before stack set fails
- Retain Stacks: retains stacks in certain accounts

## Use Cases

- Enabling AWS config across many accounts
- MFA, EIPS, EBS Encryption
- Create IAM roles for cross-account access
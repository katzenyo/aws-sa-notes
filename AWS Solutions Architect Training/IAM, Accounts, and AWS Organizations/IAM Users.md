>[!Definition] IAM Users
>IAM Users are an identity used for anything requiring long-term AWS access, such as Humans, Applications, or service accounts
>- If you can imagine a named thing, then 99% of the time the correct use case is an IAM User

- Principle, initially unidentified
	- Can be an individual person, computer, service, or group of those things
	- Must be authenticated and authorized against an IAM identity before it can do anything
		- An IAM user is an example of an IAM identity

>[!Definition] Authentication
>- Process where the principal proves to IAM that it is the identity it claims to be
>- Accomplished using either username/password or access keys
>	- Both are long-term credentials
>	- Username/password is typically used by humans
>	- Access keys typically used by applications or human using AWS CLI

>[!Definition] Authenticated Identity
> - An authenticated identity has proved to AWS that it's the identity it claims to be
> - AWS can now apply policy documents to the identity after it's become authenticated

>[!Definition] Authorization
>IAM checking the statements that apply to the identity, and either allowing or denying access

## Amazon Resource Names (ARNs)

- Uniquely identify resources across any AWS accounts
- Several different formats: 
	- `arn:partition:service:region:account-id:resource-id`
	- `arn:partition:service:region:account-id:resource-type/resource-id`
	- `arn:partition:service:region:account-id:resource-type:resource-id
	- Bucket ARN example: `arn:aws:s3:::catgifs`
	- All objects within a bucket: `arn:aws:s3:::catgifs/*`
		- Both required for granting access to bucket and objects within
		- Since bucket names are globally unique, specifying regions and account IDs are not necessary for S3 buckets

>[!Important] Exam PowerUp!
>- 5,000 IAM users per account limit
>	- If system requires more than 5k IAM identities, then you can't use a single IAM user for each identity
>	- Limiting for Internet-scale apps or very large organizations
>	- Instead, IAM Roles & Identity Federation can be used
>- IAM User can be a member of 10 groups max

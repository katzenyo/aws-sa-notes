>[!Important] Key Point
>S3 is private by default
> - only the account root user of the account owning the bucket has initial access
> - permissions otherwise must be explicitly granted

>[!Warning] Exam PowerUp!
> - When to use which policy?
> 	- Identity policies
> 		- For controlling different resources
> 		- If you have a preference for IAM
> 		- If you're controlling access from within the same account
> 	- Resource policies
> 		- If you're only controlling access to S3
> 		- If you require anonymous or cross-account access
> 	- ACLs
> 		- Never use them unless there is no other choice

## S3 Bucket Policy

- A form of resource policy
- Similar to identity policies but attached to a bucket instead
- Resource perspective permissions instead of identity perspective
	- Identity policy: controls what an identity can access
		- Can only be attached to identities in your own account
		- No ability to give identities in another account access to an S3 bucket
	- Resource policies: controls who can access the resource
		- Allow/deny access from identities in other accounts (i.e. overcome the limitation of identity policies)
		- Allow/deny anonymous principals (anonymous access to a bucket)
- If the **Principal** component is present in the policy statement, it's likely a Resource policy, as in the following example:

```json {
"Version": "2012-10-17",
"Id": "PutObjPolicy",
"Statement": [{
  "Sid": "DenyObjectsThatAreNotSSEKMS",
  "Principal": "*",
  "Effect": "Deny",
  "Action": "s3:PutObject",
  "Resource": "arn:aws:s3:::DOC-EXAMPLE-BUCKET/*",
  "Condition": {
    "Null": {
      "s3:x-amz-server-side-encryption-aws-kms-key-id": "true"
    }
  }
}]
}
```

In this example, every object written to the bucket is required to have server-side encryption using AWS Key Management Service keys, and it applies to all principals.

- Bucket policies should be default choice when granting anonymous or external account access to objects in buckets
- Can be used to set default permissions for a bucket
- Can only be one resource policy on a bucket, but it can contain multiple statements

## Access Control Lists (ACLs)

- ACLs can be on objects and buckets
- They're considered a subresource
- Legacy: AWS doesn't recommend using them
- Inflexible, only allow simple permissions
- Ignore they exist, they're basically useless

## Block Public Access

- Override bucket policies but only for public access
>[!Warning] Exam PowerUps
> - Possible to create presigned URL for an object you have no access to
> 	- The presigned URL will have the same level of access you do (e.g. none)
> 	- Can create presigned URLs for objects that don't exist
> - Permissions match the identity that created it
> - Access denied means the generating ID never had access or doesn't currently have access
> - Don't generate a presigned URL with a role
> 	- Temp creds can expire before presigned URL does
> 	- Always use long-term identities to generate

- Grants access to an object within a bucket using your own creds in a safe/secure way
- 3 main (non-ideal) ways to grant anonymous access:
	- Provide mystery user an AWS identity
	- Provide AWS credentials
	- Make bucket or object public
- Presigned URLs are an ideal way to grant access
- Often used when offloading media into S3 or as part of serverless architecture
- Time-limited
- Encode all authentication information in the presigned URL
- Can be used to upload/download objects from S3
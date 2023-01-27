>[!Important]
> - Buckets themselves cannot be encrypted
> - Only objects within buckets can be encrypted

- Encryption at rest
	- Client-side encryption
		- Objects are encrypted before reaching the server
	- Server-side encryption
		- Objects are plaintext in transit, encrypted after reaching the server
		- S3 must be trusted to handle encryption tasks
- Encryption in transit: default for S3

## Types of Encryption

- Server-side encryption with Customer-provided Keys (SSE-C)
- Server-side encryption with Amazon S3-managed Keys (SSE-S3)
- Server-side encryption with KMS Keys stored in AWS Key Management service (SSE-KMS)

## SSE-C

- Users/app
	- manage the keys
	- Supply both the plaintext and key to the S3 endpoint
- S3 endpoint
	- manages the encryption
	- Hashes the key one-way and attaches to object
- S3 storage
	- Stores the object and one-way hash
- Requires management of keys but retains control over the process

## SSE-S3 (AES256)

- Users/app
	- Provide only the plaintext data
- S3 endpoint
	- Manages encryption and the keys
	- Creates a root key
		- Root key is used to encrypt unique object key
	- Unique key generated for each object uploaded
		- Key is used to encrypt plaintext object
- S3 storage
- Default in most cases
	- Uses strong AES256 encryption
	- Little required from customer

- Three major issues
	- Not suitable for a regulatory environment that restricts access to keys
	- If keys require rotation
	- If role separation is required
		- S3 admins possess permissions to decrypt and view data
		- Not easy to implement role separation with SSE-S3

## SSE-KMS

- Similar to SSE-S3 but key management is handled by KMS
- When objects are uploaded, S3 creates KMS managed key
	- KMS key is used to generate unique encryption key for every object
- Can create customer-managed key
- Allows fine-grained control of roles and access

Method | Key Mgmt | Encryption Processing | Extras
--- | --- | --- | ---
Client-side | You | You | |
SSE-C | You | S3 | |
SSE-S3 (AES256) | S3 | S3 | |
SSE-KMS | S3 & KMS | S3 | Rotation Control & Role Separation

## Bucket Default Encryption

- Specific header for PUT operation: `x-amz-server-side-encryption`
	- Enables server-side encryption
	- If AES256 is specified, it automatically uses SSE-S3
	- If `aws:kms` is specified, it uses SSE-KMS
- All above is set on a per object basis unless a default for the bucket is specified
- Object settings take priority over bucket defaults
- Bucket policy can be used to restrict type of encryption used
>[!important] For Exams
>- FIPS 140-2 (Level 2) compliant service
>	- US security standard

>[!Abstract] Overview
>- Regional & Public service
> 	- AWS Public Zone
> 	- Requires permissions to access
> - Create, store, and manage crypto keys
> - Supports Symmetric and asymmetric keys
> - Supports cryptographic operations (encrypt, decrypt, etc)
> - **Keys can never leave KMS**

## KMS Keys

>[!Abstract] "Key" Points
>- KMS keys are isolated to region & never leave that region
>	- Multi-regions keys are possible
>- Keys are either AWS-owned or customer-owned
>	- Customer owned: either AWS-managed or customer-managed
>	- Customer owned: more configurable, i.e. cross-account access
>- Support key rotation
>- Contains backing key (and previous backing keys)
>- Aliases: shortcut to keys

- Can be used by users, services, apps
- Logical: contains ID, date, policy, desc & state
- Backed by physical key material
- Can be generated or imported
- Used for working with small sets of data or generating other keys
	- Can be used to encrypt/decrypt data up to 4KB in size

- Nothing stored in plaintext at rest
- Decrypt operations
	- KMS key doesn't need to be specified
		- Already encoded in the data's ciphertext
- Permissions to encrypt, decrypt, and generate keys are all separate

## Data Encryption Keys (DEKs)

>[!Important] Key Things
> - KMS doesn't handle encrypt/decrypt operations
> 	- You or the service interacting with KMS does
> 	- Same with tracking KMS usage

- GenerateDataKey operation
	- Works on sizes greater than 4KB
- KMS doesn't store the data encryption key at all
	- Is provided and then discarded after
- Two versions of DEKs
	- Plaintext version
	- Ciphertext (encrypted) version
- Encrypt data using plaintext DEK
- Discard plaintext version of the DEK
- Encrypted key is stored along with encrypted data

## Key Policies & Security

- Key Policies (type of [[S3 Security (Resource Policies & ACLs)|resource policy]])
	- Every key has a key policy
	- Can be changed on customer-managed keys
	- Prerequisite for granting access via [[IAM Identity Policies]]
- Key policies + [[IAM Identity Policies]]
- Key policies + Grants
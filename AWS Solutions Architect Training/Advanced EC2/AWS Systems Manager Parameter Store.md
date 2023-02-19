
## SSM Parameter Store

- Storage for configuration & secrets
	- Parameter types
		- String - any string value
		- StringList - comma delimited list of strings
		- SecureString - encrypt sensitive data using KMS keys from an AWS account
	- Can store license codes, database, strings, full configs & passwords
	- Hierarchies & versioning
	- Plaintext and ciphertext
		- Ciphertext requires KMS and KMS permissions
	- Public parameters
		- Latest AMIs per region
- Public service
	- Used by AWS service or must have access to AWS endpoints
- Changes to parameters in the parameter store can initiate events in other AWS products

- Data security and data privacy service
- Helps discover, monitor, and protect data stored in S3 buckets
- Automated discovery of data
	- PII (personally identifying info), PHI (personal health info), and financial data
- Managed Data Identifiers
	- Built-in to Macie
	- Uses Machine Learning and patterns to identify information
- Custom Data Identifiers
	- Ideal for identifying properietary information
	- Regex (regular expression) based
- Integrates with Security Hub & 'finding events' to EventBridge (most common use)
- Centrally manage
	- Either via AWS organization or a single Macie account inviting

## Architecture

![[Pasted image 20230318152606.png]]

## Identifiers

 - [Managed data identifiers](https://docs.aws.amazon.com/macie/latest/user/managed-data-identifiers.html)
	 - Maintained by AWS
	 - Identifies via list of sensitive data types
	 - Credentials, finance, health, personal identifiers, etc
- [Custom data identifiers](https://docs.aws.amazon.com/macie/latest/user/custom-data-identifiers.html)
	- Uses regex (patterns to match data)
	- Keywords - optional sequences that need to be in proximity to regex match
	- Maximum match distance - how close keywords are to regex pattern
	- Ignore words - if regex match contains ignore words, it's ignored

## Findings

- [Policy Findings](https://docs.aws.amazon.com/macie/latest/user/findings-types.html#findings-policy-types)
	- Examples: changing public, encryption, or shared settings on an S3 bucket policy
- [Sensitive Data Findings](https://docs.aws.amazon.com/macie/latest/user/findings-types.html#findings-sensitive-data-types)
	- Examples: S3 object credentials, custom identifiers, financial, multiple, and personal
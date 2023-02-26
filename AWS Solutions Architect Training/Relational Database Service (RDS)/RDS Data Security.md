>[!Warning] On the Exam
> - SSL/TLS (in transit) is available and often mandatory
> - RDS supports EBS volume encryption (KMS)
> - encryption can't be removed
> - RDS MSSQL and RDS Oracle support Transparent Data Encryption (TDE)
> - RDS Oracle supports integration with CloudHSM

- Handled by HOST/EBS
- AWS or customer managed CMK generates data keys
 - Data Keys used for encryption operations
 - Storage, Logs, Snapshots, & replicas are encrypted
 - Transparent Data Encryption (TDE) is handled within the DB engine
 - Much stronger key controls (even from AWS)

## RDS KMS Encryption & TDE Architecture

![[Pasted image 20230226010842.png]]

## IAM Authentication

>[!Warning] On the Exam
> - Policy is attached to Users or Roles that map that IAM identity onto the local RDS DB account
> 	- DB Account is configured ot use AWS Authentication Token
> 	- `generate-db-auth-token`: creates a token with 15 minute expiration, used in place of DB user password
> - Authorization is controlled by the DB engine itself
> 	- Permissions are assigned to the local DB user
> 	- IAM is not used to authorize, only to authenticate

![[Pasted image 20230226011327.png]]
## Key Points

- Multi-AZ
	- Resilient and scalable
- Provisioned server per hour $ + data transferred $
- FTP and FTPS
	- Directory Service or Custom IDP only
- FTP
	- VPC only (cannot be public)
- AS2 VPC Internet/internal only
- Ideal for:
	- If you need access to S3/EFS, but using existing protocols:
	- integrating with existing workflows
	- Using Managed File Transfer Workflows to create new ones

- Managed file transfer service
	- Supports transfers to and from S3 and EFS
- Provides managed "servers" which supports protocols
- File Transfer Protocol (FTP)
	- Unencrypted file transfer
- FTPS
	- FTP with TLS encryption
- SFTP
	- FTP over SSH
- Applicability Statement 2 (AS2)
	- Structured B2B Data
- Supports Identities
	- Service managed, Directory Service, or Custom (Lambda/API Gateway)
- Managed File Transfer Workflows
	- Serverless file workflow engine

## Architecture

![[Pasted image 20230318120107.png]]

### Endpoint Type

![[Pasted image 20230318120337.png]]

>[!Abstract] Overview
> - Data transfer service to and from AWS
> - Ideal for:
> 	- migrations, data processing transfers, archival/cost effective storage, or disaster recovery/backups
> 	- designed to work at *huge scale*
> - Maintains metadata (permissions, timestamps, etc)
> - Built in data validation

>[!Abstract] Key Features
> - Scalable
> 	- 10Gbps per agent (~100TB per day)
> - Bandwidth Limiters
> 	- Avoids link saturation
> - Incremental and scheduled transfers
> - Compression and encryption
> - Automatic recovery from transit errors
> - AWS service integration
> 	- S3, EFS, FSx
> - Pay as you use, per GB

## Architecture

![[Pasted image 20230317160803.png]]

## Components

- Task
	- A job within DataSync
	- Defines what is being synced, how quickly, and from/to where
- Agent
	- Software used to read/write to on-prem data stores using NFS or SMB
- Location
	- Every task has two locations: from and to
	- E.g. NFS, SMB, Amazon EFS, FSx, and Amazon S3
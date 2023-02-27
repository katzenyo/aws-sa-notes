
- Managed DB migration service
- Runs using a replication instance
- Source and Destination endpoints
	- Point at Source and Target DB's
- One endpoint MUST be on AWS
- Safe default option for any DB migration with at least one DB in AWS
- No downtime

## Architecture

- Source DB (at least one must be in AWS)
- Supports MySQL

![[Pasted image 20230226212737.png]]

## Schema Conversion Tool (SCT)

>[!Warning] On the Exam
>- **ONLY** Used when converting one DB engine to another
>	- Including DB -> S3 (migrations using DMS)
> - SCT is **not** used when migration between DB's of the same type
> 	- On prem MySQL -> RDS MySQL

- Works with OLTP DB Types
	- On-prem MSSQL -> RDS MySQL
- Works with OLAP
	- On-prem Oracle -> Aurora

## DMS & Snowball

- Larger migrations, multi-TB in size
	- Moving data over networks takes time and consumes capacity
- DMS can utilize snowball
	1. Use [[Database Migration Service (DMS)#Schema Conversion Tool (SCT)|SCT]] to extract data locally, move to snowball device
	2. Ship device back to AWS, where it's loaded onto an S3 bucket
	3. DMS migrates from S3 into the target store
	4. Change Data Capture (CDC) can capture changes, and via S3 intermediary they are also written to the target database
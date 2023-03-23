>[!Warning] On the Exam
> - Redshift Enhanced VPC Routing
> 	- VPC Networking
> 	- Required for customized network requirements

## Basics

- Petabyte-scale data warehouse
	- Designed for analytics, not operational usage
- [[Database Refresher & Models#Column Databases|OLAP (Column based)]] database
	- NOT OLTP (row/transaction)
- Pay as you use
	- [[Relational Database Service (RDS) Architecture#Costs/Billing|Similar billing structure to RDS]]
- Direct query S3 using Redshift Spectrum
- Direct Query of other databases using federated query
- Integrates with AWS tooling suhc as Quicksight
- SQL-like interface
	- JDBC/ODBC connections

## Architecture

- Server-based
	- Not serverless
- Cluster is a private network
	- Most of it can't be accessed directly
- Single AZ in a VPC
	- Network cost/performance
- Leader Node
	- Query input, planning, and aggregation
- Compute Node
	- Performing queries of data
- VPC Security, IAM permissions, KMS at rest encryption, CloudWatch monitoring
- AWS services
	- [[Kinesis Data Firehose|Firehose]] can stream data into Redshift
	- [[Database Migration Service (DMS)|DMS]] can migrate data into Redshift
- Automatic snapshots to S3 (8 hours, 5GB) with retention
	- Manual snapshots to S3 supported

![[Pasted image 20230323112251.png]]

## Resilience and Disaster Recovery

- Automatic incremental backups
	- Either every 8 hours or 5GB of data
	- 1-day retention period by default
		- Configurable up to 35 days
- Manual snapshots can be taken at any time
	- Can be deleted manually as required
- Redshift can be backed up into S3 to protect against AZ failure
	- Snapshots can be configured to another region for DR
		- Supports  separate configurable retention period
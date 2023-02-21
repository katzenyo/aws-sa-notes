
- Database as a Service (not the case)
	- Database Server as a Service (DBSaaS)
	- Multiple DB on one DB server (instance)
- Choice of DB engines
	- MySQL
	- MariaDB
	- PostgreSQL
	- Oracle
	- Microsoft SQL Server
- Amazon Aurora is a different product
- Managed service
	- No access to OS or SSH Access
		- Unless using RDS Custom

## Architecture

>[!Warning] On the Exam
> - Subnet Group
> 	- The subnets that RDS is allowed to use
> - Each RDS instance can have multiple databases on them
> - Each RDS instance is provided dedicated EBS storage
> - Read Replicas
> 	- use asynchronous replication
> 	- Used to scale read load or resilience if needing to recover into a different region
> - Backups & snapshots are sent to S3

![[Pasted image 20230221145916.png]]

## Costs/Billing

- Billed for resource allocation:
	1. Instance Size & Type
	2. Multi AZ or not
	3. Storage type & amount
	4. Data Transferred ($ per GB)
	5. Backups & Snapshots (First 2TB free)
	6. Licensing (if applicable)
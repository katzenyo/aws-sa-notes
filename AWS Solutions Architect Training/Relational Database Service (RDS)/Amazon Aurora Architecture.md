- Very different from RDS
	- Uses a Cluster
- Single primary instance + 0 or more replicas
	- Replicas can provide both read scaling and availability
- No local storage
	- Uses cluster volumes
- Faster provisioning, improved availability, and improved performance

## Architecture

![[Pasted image 20230226125725.png]]

- Entirely SSD based
	- High IOPs, low latency
- Storage based on what's consumed
- High water mark
	- Billed for the most used
- Storage which is freed can be reused
- Replicas can be added and removed without requiring storage provisioning

## Endpoints

- Cluster Endpoint
	- Always points at primary instance
	- Used for read/write
- Reader Endpoint
	- Only reads but load balances across available replicas
	- Better read scaling

## [Billing](https://aws.amazon.com/rds/aurora/pricing/)

- No free tier option
- No support for Micro Instances
- Better value than RDS single AZ (micro)
- Compute
	- Hourly charge, per second, 10 min minimum
- Storage
	- GB/month conusmed, IO cost per request
- 100% DB size in backups are included

## Aurora Restore, Clone, and Backtrack

- [[RDS Backup and Restore|Backups work the same as in RDS]]
- Restores create a brand new cluster
- Backtrack
	- Allows in-place rewinds to a previous point in time
	- Must be enabled on per cluster basis
- Fast clone
	- Make a new database much faster than copying all the data
	- Stores only the difference (delta) between copies


## MultiAZ Instance Deployment

>[!Warning] On the Exam
> - Primary instance is synchronously replicated to a standby instance in another AZ
> - Backups/snapshots stored in S3 buckets across multiple AZs
> 	- Backups can be taken from standby to improve performance

- Replication method:
	- MAriaDB, MySQL, Oracle, PostgreSQL use Amazon Failover tech
	- Microsoft SQL uses SQL Server database mirroring
- Database CNAME
	- Points at primary database instance
- Automatic failover
	- CNAME changes to point at standby DB
	- Takes 60-120 secs to occur
		- Affected by DNS caching
	- Failover reasons: AZ Outage, Primary failure, manual failover, instance type change, and software patching
- Not free tier
	- Extra costs for the replica
- One Standby replica only
	- Can't be used for reads or writes
- MultiAZ is same region only
	- But different AZs in the same region

## MultiAZ Cluster

>[!Warning] On the Exam
> - Synchronous replication of one writer DB instance in one AZ into two Reader DB instances in two other AZs
> 	- Two readers only
> - Replicated data is committed when at least 1 Reader finishes writing
> - Cluster Endpoint 
> 	- points at the writer and is used for reads, writes, and administration
> - Reader Endpoint
> 	- Directs any reads towards an available reader instance
> - Instance Endpoints
> 	- point at a specific instance
> 	- Generally used for testing/fault finding

- 1 Writer and 2 Reader DB instances (in different AZs)
	- Can be used to scale read workloads since each Reader and the Writer instances are read-capable
	- Much faster hardware, uses Graviton + local NVME SSD storage
	- Fast writes to local storage that's then flushed to EBS
- Replication via transaction logs
- Failover is faster ~35s + transaction log apply
- Writes are "committed" when 1 reader is confirmed
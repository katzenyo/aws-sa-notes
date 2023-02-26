
## Backups

### General

- Automated backups
- Snapshots
	- First snapshot is a full snapshot of all consumed data
	- Subsequent snapshots are incrementals
	- Snapshots must be deleted manually
- AWS Managed S3 buckets for S3

### Cross-Region

- RDS can replicate backups to another region
	- Both snapshots and transaction logs
- Charges apply for the cross-region data copy and the storage in the destination region
- Cross-Region is not default
	- Must be configured within automated backups

## Restores

- Restores create a brand new RDS instance with a new address
- Snapshots are taken in a single point of time (creation time)
- Automated = any 5 minute point in time
- BAckup is restored and transaction logs are replayed to bring DB to desired point in time
	- Achives good [[RPO and RTO|RPO]]
- Restores aren't fast
	- Think about [[RPO and RTO|RTO]]
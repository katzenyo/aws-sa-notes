https://aws.amazon.com/backup-restore/services/

- Fully managed data protection (backup/restore) service
- Consolidate mgmt into one place
	- Across accounts & regions
- Supports many AWS products
	- Compute, block, object, & file storage, databases

## Components

- Backup Plans
	- Configure frequency, window, lifecycle, vault, region copy
	- Cold storage: 90 day min storage
- Resources being backed up
- Vaults
	- Backup destination (container)
	- assign KMS key for encryption
- Vault Lock
	- Write once, read many (WORM)
	- 72 hour cool off, then AWS can't even delete it
- On-demand backups as needed
- PITR (point in time recovery)
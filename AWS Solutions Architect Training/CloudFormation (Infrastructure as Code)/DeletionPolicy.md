
- If a logical resource is deleted from a template, the physical resource is deleted
	- Can cause data loss
- With deletion policy, you can define on each resource Delete, Retain, or Snapshot
- Supports EBS Volume, ElastiCache, Neptune, RDS, and Redshift for snapshots
- Snapshots continue past stack lifetime
	- Must be cleaned up separately
- DeletionPolicies only applies to delete, not replace operations

## Architecture

![[Pasted image 20230320135555.png]]
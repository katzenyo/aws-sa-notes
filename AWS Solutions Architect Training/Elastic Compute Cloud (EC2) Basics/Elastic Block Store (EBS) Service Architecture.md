>[!Warning] On the Exam
> - EBS storage is provisioned in ONE AZ (it is AZ resilient only)
> 	- EBS volumes in different AZs cannot communicate with each other

- Block Storage: raw disk allocations (volume)
	- Can be encrypted using [[Key Management Service]]
	- Instances see block device and create file system on the device (ext3/4, xfs)
- Storage is provisioned in ***ONE AZ*** (Resilient in the single AZ)
- Attached to one EC2 instance (or other service) over a storage network
	- Detached and reattached, not lifecycle linked to one instance - persistent
- Snapshot (backup) into [[Simple Storage Service (S3) Basics]]
	- Create volume from snapshot (migrate **between AZs**)
	- Snapshot is stored into S3, which is available across all regions - HA
	- Snapshots can be copied to S3 in another region then used to create a new EBS volume in an AZ in that region
- Different physical storage types, different sizes, and different performance profiles
- Billed based on GB-month (and in some cases performance)

## Architecture

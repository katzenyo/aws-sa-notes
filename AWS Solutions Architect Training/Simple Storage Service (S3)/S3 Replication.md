>[!Warning] On the Exam
> - Replication is not retroactive
> - Versioning must be enabled on both buckets
> - Replication is one-way only (source to destination)
> - Unencrypted by default
> 	- Supports SSE-S3 & SSE-KMS with extra config
> 	- Cannot replicate objects using SSE-C since S3 lacks keys required to access plaintext version
> - Source bucket owner needs permissions to objects
> - Cannot replicate system events, Glacier, or Glacier Deep Archive
> - Delete markers cannot be replicated across buckets

>[!Important] Use Cases
> - SRR - Log Aggregation
> - SRR - Prod and test account syncs
> - SRR - Reslience with strict sovereignty reqs, account level isolation
> - CRR - Global REslience Improvements (backups
> - CRR - Latency Reduction

- Cross-Region Replication (CRR)
	- Replicates data from a bucket in one region to a bucket in another region
- Same-Region Replication (SRR)

## Process

- Replication configuration is applied to source bucket
- IAM role is configured in a trust policy for the S3 service to assume the role
	- Role grants permissions to S3 to read and replicate objects from source bucket to destination bucket
- Encrypted via SSL
- For replication across AWS accounts:
	- Destination bucket must have bucket policy that allows role in the source account to replicate objects

## Replication Options

- Replication
	- Default: replicate all objects (or subset) to a destination bucket
- Storage Class
	- Default: storage class is to maintain existing storage class from the source
- Ownership
	- Default is the same ownership as source account
	- If different accounts, objects in destination bucket will be owned by source bucket account
- Replication Time Control (RTC)
	- Adds guaranteed 15-minute SLA to maintain synchronization
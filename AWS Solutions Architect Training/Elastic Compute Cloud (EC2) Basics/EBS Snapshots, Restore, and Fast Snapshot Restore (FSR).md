
>[!Warning] On the Exam
> - New EBS Volume = full performance immediately available
> - Snapshots are restored lazily: they are fetched gradually
> - Requested blocks are fetched immediately
> - Force a read of all data immediately
> - Fast Snapshot Restore (FSR) - immediate restore
> 	- Up to 50 snaps per region
> 	- **Set on the Snapshot & AZ**
> 	- Costs extra, can get expensive

- Incremental volume copies to [[Simple Storage Service (S3) Basics]]
- First snapshot is a full copy of 'data' on the volume
	- Initial snapshot is data used, not full volume
- Future snapshots are incremental
	- If a snapshot is deleted, all snapshots taken after that particular snapshot will still function
- Volumes can be created (restored) from snapshots
- Snapshots can be copied to another region
	- Great for data migration

## Snapshot Architecture Example

![[Pasted image 20230211193649.png]]

## Snapshot Consumption & Billing

- Billed using gigabyte per month metric
	- A 10GB snapshot stored for 1 month = a single 10GB month
	- A 20GB snapshot stored for 0.5 months = a single 10GB month
	- Used data, not allocated data

![[Pasted image 20230211194158.png]]
- Direct (local) attached storage - storage directly on the EC2 host (instance store)
	- If disk fails, hardware fails, if instance moves between host = storage lost
- Network attached storage - volumes delivered over network
	- [[Elastic Block Store (EBS) Service Architecture|Elastic Block Store (EBS)]]
- Ephemeral storage - temporary storage
	- Instance store (physical storage attached to an EC2 host)
- Persistent storage - permanent storage, lives on past the lifetime of the instance

## Key Terms

- Block Storage: volume presented to the OS as a collection of blocks
	- Mountable and bootable
	- No structure provided
	- High performance storage inside an OS
- File Storage: presented as a file share
	- Mountable
	- Not bootable
	- Has structure
- Object Storage: collection of objects
	- Flat structure
	- Not mountable
	- Not bootable

## Storage Performance

- IO (block) Size
	- 16k - 1MB size
- IOPS
	- Reads/writes of blocks per second
- Throughput
	- Measured in MB/s
- IO Size times IOPS = Throughput
	- e.g. 16KB x 100 IOPS = 1.6MB/s throughput
		- ...unless throughput cap exists
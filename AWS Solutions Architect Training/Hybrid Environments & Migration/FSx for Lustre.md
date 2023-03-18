
- Managed Lustre
	- Designed for HPC, Linux Clients (POSIX compatible)
- Machine learning, big data, financial modeling
- 100's GB/s throughput, sub millisecond latency
- Deployment types
	- Scratch
		- Highly optimized for short term
		- No replication
		- Fast
	- Persistent
		- Longer term
		- High availability (in one AZ only)
		- Self-healing
- Accessible over VPN or Direct Connect

## Architecture

- Metadata stored on Metadata Targets (MST)
- Objects stored on called object storage targets (OST)
	- 1.17TB
- Baseline performance based on size
	- min of 1.2TB then increments of 2.4TB
	- **Scratch**: base 200 MB/s per TB of storage
	- **Persistent**: 50MB/s, 100MB/s, and 200MB/s per TB of storage
- Burst up to 1,300 MB/s per TB (credit system)

![[Pasted image 20230317201455.png]]

## Key Points

- Scratch
	- Designed for pure performance
	- Short term, temp workloads
	- No HA, no replication
	- Larger file systems = more servers, more disks, more chance of failure
- Persistent
	- Replication **within a single AZ only**
	- Auto-heals when hardware failure occurs
- Backup to S3 supported for both
	- Manual or automatic w/ 0-35 day retention
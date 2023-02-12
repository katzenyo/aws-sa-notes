
## General Purpose SSD - GP2

>[!Warning] On the Exam
> - Ideal for
> 	- Boot volumes
> 	- Low latency interactive apps
> 	- Dev/test environments
> - Currently default but will be replaced by GP3

- Volumes range from 1GB to 16TB
- IO credit is 16KB
	- IOPs assume 16KB
	- 1 IOPS is 1 IO in 1 second
- IO bucket
	- capacity of 5.4 million IO credits, all volumes start with this amount
		- Allows for 30 min @ 3,000 IOPS
		- Ideal for boots and initial workloads
	- Fills at rate of baseline performance
		- Min of 100 IO credits per second, regardless of volume size
		- Beyond the 100 min, buckets fill with 3 IO credits per second per GB of volume size
	- Can burst up to 3,000 IOPS by depleting the bucket
	- Volumes larger than 1TB receive a baseline above burst
		- Credit system isn't used and you always achieve baseline
		- Up to maximum 16,000 IO credits per second baseline (GP2)

## General Purpose SSD - GP3

>[!Warning] On the Exam
> - Ideal for:
> 	- Virtual desktops
> 	- Medium sized single instance databases (MSSQL Server, Oracle DB)
> 	- Low-latency interactive apps
> 	- Dev/test environments
> 	- Boot volumes

- By default starts with 3,000 IOPs & 125 MB/s
- Volumes range from 1GB to 16TB
- 20% cheaper than GP2 base price
- 4x faster max throughput than GP2
	- 1000MB/s vs 250MB/s for GP2

## Provisioned IOPS SSD (io1 & io2)

>[!Warning] On the Exam
> - Ideal for:
> 	- Consistent low latency & jitter
> 	- High performance, latency-sensitive workloads
> 	- I/O-intensive NoSQL & relational databases
> 	- When you need smaller volumes but higher performance
> 		- Only achievable with io1, io2, and io2 Block Express

- With io1/2/BlockExpress, IOPS can be adjusted independently of size

### io1/2
- Up to 64,000 IOPs per volume (4x the amount of GP2/3)
- Up to 1,000 MB/s throughput
- 4GB to 16TB with io1/2
- io1 50 IOPs/GB (max)
- io2 500 IOPs/GB (max)
- io1 - 260,000 IOPs & 7,500MB/s (per instance performance limit)
- io2 - 160,000 IOPs & 4,750MB/s (per instance performance limit)

### BlockExpress
- Up to 256,000 IOPs per volume (Block Express)
- Up to 4,000 MB/s throughput (Block Express)
- 4GB to 64TB with BlockExpress
- 1000 IOPs/GB (max)
- io2 Block Express - 260,000 IOPs & 7,500MB/s (per instance performance limit)

## Hard Disk Drive (HDD)-based (platters)

### st1 - Throughput Optimized

>[!Warning] On the Exam
> - Ideal for:
> 	- Big data
> 	- Data warehouses
> 	- Log processing
> 	- Frequent access, throughput-intensive, and sequential workloads

- Cheap
- From 125GB to 16TB in size
- Max 500 IOPs (1MB)
- Max 500MB/s throughput
- Baseline performance
	- 40MB/s per TB base
	- 250MB/s per TB burst

### sc1 - Cold HDD

>[!Warning] On the Exam
> - Ideal for:
> 	- Colder data requiring fewer scans per day
> 	- Less frequently accessed workloads

- Cheaper, lowest cost HDD volume
- From 125GB to 16TB
- Max 250 IOPs (1MB)
- Max 250 MB/s throughput
- 12MB/s per TB Base
- 80MB/s per TB burst
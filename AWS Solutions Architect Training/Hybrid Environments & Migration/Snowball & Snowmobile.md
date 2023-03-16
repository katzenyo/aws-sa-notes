
>[!Important] Key Concepts
> - Move large amounts of data in and out of AWS
> - Physical storage
> 	- Suitcase or truck
> - Ordered from AWS Empty, Load up, Return
> - Ordered from AWS with data, empty, and return


## Snowball

>[!Warning] On the Exam
> - When to use:
> 	- 10TB to 10PB economical range (multiple devices)
> 	- Multiple devices can be sent to multiple premises
> 	- Storage device only

- Ordered from AWS, log a job, device must be delivered
- Data encryption using KMS
- 50TB or 80TB capacity
- 1 Gbps or 10Gbps network connection required

## Snowball Edge

>[!Warning] On the Exam
> - Provides both storage and compute
> - Ideal for:
> 	- Remote sites
> 	- Where data processing on ingestion is required

- Larger capacity over Snowball
- 10Gbps, 10/25, 45/50/100 Gbps
- Storage optimized
	- 80 TB, 24vCPU, 32GB RAM (1 TB SSD with EC2)
- Compute Optimized
	- 100TB + 7.68 NVME, 52 vCPU, 208GB RAM
- Compute with GPU
	- Same as above, but with GPU

## Snowmobile

>[!Warning] On the Exam
> - Ideal for:
> 	- Single location with 10 petabytes or more of data
> 		- Not great for multi-site or less than 10PB

- Portable datacenter inside a shipping container delivered by truck (literally)
- Special order only
- Store up to 100PB of data per snowmobile
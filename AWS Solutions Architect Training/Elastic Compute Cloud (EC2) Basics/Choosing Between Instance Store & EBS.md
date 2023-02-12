>[!Warning] On the Exam
> - Use EBS (avoid instance store) for:
> 	- Persistence
> 	- Resilience
> 		- Can snapshot to S3
> 	- Storage isolated from instance lifecycles
> - Use Instance Store for:
> 	- Super high performance needs
> 	- If cost is primary concern, since it's included
> - Use case depends if:
> 	- Resilience within the app with in-built replication
> 	- High performance needs
> - For cheap persistence, use ST1 or SC1
> - For throughput or streaming use ST1
> - For boot loads, never use ST1 or SC1
> - GP2/3: up to 16,000 IOPs (max)
> - IO1/2: up to 64,000 IOPs (256,000 for Block Express) (max)
> - RAID0 + EBS up to 260,000 IOPs (io1/2-BE/GP2/3) (max)
> 	- Consider max performance of volumes and instance together
> - Greater than 260,000 IOPs: use instance store
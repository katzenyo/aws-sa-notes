- Cluster placement groups
	- Pack instances close together
- Spread placement groups
	- Keep instances separated
- Partition placement groups
	- Groups of instances spread apart


## Cluster Placement Groups

>[!Warning] On the Exam
> - Cannot span AZs
> 	- **One single AZ only**
> 	- Locked into when launching the first instance
> - Can't span VPC peers
> 	- Impacts performance
> - Requires supported instance type
> - Use same type of instance
> - Launch at the same time - not mandatory but highly recommended
> - 10Gbps single stream performance
> - Ideal for:
> 	- Performance loads
> 	- Fast speeds
> 	- Low latency

- Launch all instances in the group simultaneously
- Must be launched in a single AZ
	- Cluster group is locked into the AZ that the first instance launches in
- All cluster members have direct connections to each other
	- They all occupy the same physical rack space, sometimes even the same host
	- If hardware fails, all running instances in cluster group may also fail
- 10Gbps stream
- 5Gbps normally
- Offers lowest latency and max packets per second (PPS) possible in AWS

## Spread Placement Groups

>[!Warning] On the Exam
> - Provides infrastructure isolation
> 	- Each instance is separated from other instances
> 	- Each instance runs on a different rack
> 	- Each rack has its own network and power
> - 7 instances per AZ (hard limit)
> - Spans multiple AZs
> - Not supported for Dedicated Instances or Hosts
> - Ideal for:
> 	- Small number of critical instances that need to be kept separated from each other
> 	- e.g. file servers, domain controllers
> 	- Highest possible availability

## Partition Placement Groups

>[!Warning] On the Exam
> - **7 partitions per AZ (hard limit)**
> 	- Infinite # of instances per partition
> - Instances can be placed in a specific partition or they can be auto placed
> - Ideal for:
> 	- Topology-aware applications
> 		- HDFS, HBase, Cassandra
> 	- Containing the impact of hardware failure to part of an application

- For infrastructure exceeding 7 instances per AZ but still require separate fault domains
- Created across multiple AZs
- Maximum 7 partitions per AZ
- Each partition has its own physical rack space, no sharing between partitions
- Ideal for:
	- Massive scale parallel processing systems
	- Topology aware use cases
	- HDFS, HBase, Cassandra
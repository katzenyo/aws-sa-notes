>[!Warning] On the Exam
> - Local on EC2 host only
> 	- If instance moves between hosts, instance store data is lost
> - ***MUST BE ATTACHED AT LAUNCH ONLY***
> - Lost on instance move, resize, or hardware failure
> - Highest data performance, highest risk
> - Included in the instance price
> - **Ephemeral, temporary**
> - Ideal for:
> 	- Replaceable, ephemeral, temporary data
> 	- Maximum IO

- Block Storage devices
	- Local, instead of on network
- Physically connected to a single EC2 Host
- Instances on the EC2 host can access them
- Highest storage performance in AWS
- Included in instance price
- ***MUST BE ATTACHED AT LAUNCH***
	- Cannot be attached afterwards
- When instances are moved to new hosts, the original instance storage is lost
- All instance store volumes are ephemeral
	- Should never be used for anything important
- D3 = 4.6GB/s throughput
- I3 = 16 GB/s of sequential throughput
- More IOPs and Throughput vs EBS
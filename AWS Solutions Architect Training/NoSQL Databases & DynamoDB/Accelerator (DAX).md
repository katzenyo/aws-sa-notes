>[!Warning] On the Exam
> - Primary node (writes) and replicas (reads)
> - Nodes are highly available
> 	- Primary failure = election
> - In-memory caching, scaling
> 	- Much faster reads, reduced costs
> 	- Ideal for read heavy workloads
> - Scale up and scale out (bigger or more)
> - Supports write-through
> 	- Supports read caching of items and query/scan results
> - DAX is deployed inside a VPC (not public)
> 	- Apps using DAX must also be inside the same VPC

## Traditional Cache vs DAX

![[Pasted image 20230322171831.png]]

## DAX Architecture

![[Pasted image 20230322172615.png]]
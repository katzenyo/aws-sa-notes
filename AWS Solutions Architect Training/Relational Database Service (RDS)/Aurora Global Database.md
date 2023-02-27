
## Architecture

![[Pasted image 20230226155408.png]]

- Cross-region DR and BC (business continuity)
- Global Read Scaling
	- low latency performance improvements
- 1s or less replication between region
	- unidirectional replication
- No impact on DB performance
- Secondary regions can have 16 replicas
- Can be promoted to R/W
- Currently MAX 5 secondary regions
- ACU - Aurora Capacity Unit
	- Aurora Serverless cluster has a min & max ACU
- Cluster adjusts based on load
- Can go to 0 and be paused
- Consumption billing per-second basis
- Same resilience as Aurora
	- 6 copies across AZs

## Architecture

![[Pasted image 20230226143823.png]]

- Proxy fleet brokers connections between end users and ACUs
	- Allows dynamic scaling of ACUs since proxy fleet handles connections in the foreground

## Use Cases

- Infrequently used applications
- New applications
- Variable workloads
- Unpredictable workloads
- Development and test databases
- Multi-tenant applications
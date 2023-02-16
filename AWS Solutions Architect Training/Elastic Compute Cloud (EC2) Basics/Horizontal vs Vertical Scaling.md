
## Vertical Scaling

- Resizing an EC2 instance to have larger capacity (memory, storage, compute, etc)
- Resize requires reboot
	- Causes disruption/downtime
- Larger instances carry billing premium
- Upper cap on instance size (performance)
- Simple
- No application modification required
- Works for all applications, even monoliths

## Horizontal Scaling

- Increase number of instances/hosts
- Multiple copies of an app running
- Requires use of load balancer
	- Sits between customers and systems
	- Upon attempt to access system, load is distributed across all instances
**- Sessions, sessions, sessions**
	- Every interaction with an app is handled through sessions
- Requires application support OR off-host sessions
	- Off-host sessions: session data is stored in another place, e.g. database
		- Servers are called *stateless* in this setup
- No disruption while scaling
- No real limits to horizontal scaling
- Less expensive - no large instance premium
- Supports more granularity
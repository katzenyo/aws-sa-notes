
## Concepts

- 1 additional AZ
	- No built in resilience
	- Think of them as an AZ but closer to your location
- Lower latency (due to proximity)
- Not supported by all products
	- Many are opt-in w/ limitations
- DX to a local zone is supported (for extreme performance needs)
- Utilize parent region
	- i.e. EBS snapshots to parent
- Use local zones when you need the highest performance

## Without Local Zones

![[Pasted image 20230323123426.png]]

## With Local Zones

![[Pasted image 20230323124018.png]]
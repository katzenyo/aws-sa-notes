
>[!Important] Key Points
> - AS advertises to all peers the shortest path it knows
> - AS prepends its own AS number onto the path
> 	- Creates a source dest path that BGP routers learn & propagate
> - BGP exchanges shortest ASPATH between peers
> 	- Sometimes longer paths provide better network performance
> 		- AS Path Prepending can be used to artifically lengthen a path for situations like above

- Autonomous Systems (AS)
	- Routers controlled by a single entity (network in BGP)
- Each AS is assigned a number (ASN)
	- Unique, allocated by IANA
	- Range from `0-65535`
	- Ranges `64512-65534` are private
- Operates over `tcp/179`
	- Reliable
- Peering must be manually configured, it's not automatic
- Path-vector protocol
	- Exchanges the best path to a destination between peers
	- Path is called ASPATH
- iBGP
	- Internal BGP
	- Routing *within* an AS
- eBGP
	- External BGP
	- Routing *between* AS'

## Architecture

![[Pasted image 20230315162638.png]]

- Public hosted zone that isn't public
	- Cannot be queried outside of VPCs
- Associated with VPCs
	- Only accessible within those VPCs
	- Using different accounts is supported via CLI/API
- Split-view (overlapping public & private) for public and internal use with the same zone name

## Split View (Split Horizon) Hosted Zones

![[Pasted image 20230220162328.png]]

- Ideal for hosting an internal intranet simultaneously on a public domain
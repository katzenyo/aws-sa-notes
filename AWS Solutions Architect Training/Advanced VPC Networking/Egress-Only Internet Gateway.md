## Key Points

- Internet Gateway but for IPv6
- Allows outbound only connections
- Blocks inbound connections

---

- IPv4 addresses are either public or private
	- NAT allows private IPv4s to access public networks
		- Without allowing externally initiated connections (inbound)
- IPv6: all IPs are always public
	- Internet Gateway (IPv6) allows all IPs inbound and outbound
	- Egress-Only is outbound only for IPv6

## Architecture

![[Pasted image 20230314170438.png]]
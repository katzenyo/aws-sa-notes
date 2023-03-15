>[!Warning] On the Exam
> - If an ACCEPT log entry is immediately followed by a REJECT
> - Not logged:
> 	- `169.254.169.254`
> 	- `169.254.169.123`
> 	- DHCP
> 	- Amazon DNS
> 	- Amazon Windows license

---

- Captures metadata (not contents)
	- Packet size, src/dst IP, etc
- Can be attached to:
	- VPCs
		- All ENIs in a VPC
	- Subnets
		- All ENIs in a subnet
	- ENIs directly
- **Not realtime**
- Log destinations
	- [[Simple Storage Service (S3) Basics|S3]]
	- [[CloudWatch Logs]]
	- Use Athena for querying

## Architecture

![[Pasted image 20230314020848.png]]

## Flow Log Fields

```
<version>
<account-id>
<interface-id>
<srcaddr>
<dstaddr>
<srcport>
<dstport>
<protocol>
	ICMP=1
	TCP=6
	UDP=17
<packets>
<bytes>
<start>
<end>
<action>
<log-status>
```
>[!Warning] On the Exam
> - Peering link can only be between two VPCs, no more than that
> - VPC CIDRs cannot overlap

- Direct encrypted network link between two VPCs
- Works same/cross-region and same/cross-account
- Public hostnames resolve to private IPs (optional)
- Same region security groups can reference peer security groups
- VPC Peering does NOT support transitive peering
- Routing configuration is required
	- Security groups & [[Network Access Control Lists (NACL)|NACLs]] can filter

## Architecture

![[Pasted image 20230315003018.png]]
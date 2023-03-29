>[!Important] Considerations
> - Supports transitive routing
> - Can be used to create global networks
> - Share between accounts using AWS RAM
> - Peer TGWs in one region with TGWs in another region
> 	- Same or cross account
> - Less complexity than not using TGWs

- Network transit hub that connects VPCs to on prem networks
- Significantly reduces network complexity
- Single network object
	- HA and scalable
- Attachments to other network types
	- VPC, site to site VPN, and direct connect gateway

## Architecture without Transit Gateway

![[Pasted image 20230316110427.png]]

## Architecture with Transit Gateway

- VIF = virtual interface

![[Pasted image 20230316110636.png]]
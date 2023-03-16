
- IPSec is a group of protocols
- They set up secure tunnels across insecure networks
	- Such as between two peers (local and remote)
- Provides authentication and encryption
- *interesting traffic*
	- Traffic that matches certain rules

- IPSec has two main phases
	- IKE Phase 1 (slow & heavy)
		- Authenticate - pre-shared key (password) or certificate
		- Using asymmetric encryption to agree on and create a shared symmetric key
		- IKE SA created (phase 1 tunnel)
		- Remains when interesting traffic is not present
	- IKE Phase 2 (Fast & Agile)
		- Use keys agreed on in phase 1
		- Agree on encryption method and keys used for bulk data transfer
		- Create IPSEC SA, phase 2 tunnel (running over phase 1)
		- Torn down when interesting traffic isn't present, but can be quickly re-created

## IKE Phase 1 Architecture

![[Pasted image 20230315173040.png]]

## IKE Phase 2 Architecture

![[Pasted image 20230315173234.png]]

## VPN Types

- Policy-based VPN
	- Rule sets match traffic -> a pair of Security Associations
	- different rules and security settings for different types of traffic
- Route-based VPN
	- Target matching (prefix)
	- Matches a single pair of security associations

### Route vs Policy Based VPN Architecture

![[Pasted image 20230315174106.png]]
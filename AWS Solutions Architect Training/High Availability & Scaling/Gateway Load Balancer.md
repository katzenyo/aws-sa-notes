
- When you need a transparent security appliance that scales in a multi-tenant environment across fleets and apps
- Helps run and scale 3rd party appliances
	- Firewalls, intrusion detection/prevention, analysis tools
- Transparent Inbound and Outbound traffic inspection and protection
- Two major components
	- Endpoints
		- Traffic enters/leaves via endpoints
	- Balances across multiple backend appliances
- Traffic and metadata is tunnelled using GENEVE protocol

## How it works

- Layer 3/4 device
- Uses GENEVE encapsulation to transmit data to appliances
	- Data is unaltered

## Architecture

![[Pasted image 20230303224557.png]]
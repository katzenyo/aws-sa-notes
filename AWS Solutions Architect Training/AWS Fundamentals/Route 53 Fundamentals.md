>[!Abstract] The Basics
> - Allows registration of domains
> - Hosts zones on managed nameservers
> - Global service with a single database
> - Globally resilient
> - "DNS as a service"

## Domain Registration Process

1. R53 checks the domain registry for the TLD
2. If available, R53 creates a [[DNS#Hierarchical Design|zone file]] (hosted zone)
3. Also allocates nameservers
	1. Four nameservers for every zone
2. Communicates with the registry to register the domain
3. NS records provided by registrar, indicate the four nameservers are authoritative for the domain

## Hosted Zones

- Zone files in AWS
- Hosted on four managed name seravers
- Can be public
	- Or private, for hosting private domains
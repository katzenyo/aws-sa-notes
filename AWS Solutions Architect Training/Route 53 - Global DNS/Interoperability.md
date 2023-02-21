
- Route 53 has two roles:
	- [[Route 53 Fundamentals#Domain Registration Process|Domain registrar]]
	- Domain Hosting
	- Can do both or just one
- Route 53 accepts money (domain registration fee)
	- Allocates 4 name servers (ns) (domain hosting)
	- Creates a zone file (domain hosting)
	- Communications with the registry of the TLD (domain registrar)
		- Sets the domain ns records to point at the 4 nameservers above

## Both Roles

![[Pasted image 20230220173305.png]]

## Registrar Role Only

- Rare, should not really be used

![[Pasted image 20230220173410.png]]

## Hosting Role Only

- Most common other than Both scenario

![[Pasted image 20230220173544.png]]
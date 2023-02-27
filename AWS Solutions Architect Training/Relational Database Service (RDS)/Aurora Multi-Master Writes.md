- Default Aurora mode is Single-Master
	- One R/W and 0+ Read Only Replicas
	- Cluster Endpoint is used to write, read endpoint is for load balanced reads
	- Failover takes time- replica promoted to R/W
- In Multi-Master mode all instances are R/W

## Architecture

![[Pasted image 20230226161206.png]]

## Aurora Single-Master

- Application connects to [[Amazon Aurora Architecture#Endpoints|Cluster Endpoint]]
	- Application/user can only connect to the primary
	- Primary will failover to replica DB, but this takes time

## Aurora Multi-Master

- Application can connect to both DB instances since both are writers
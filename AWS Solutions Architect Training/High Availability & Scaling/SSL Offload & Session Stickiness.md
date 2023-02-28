
## SSL Offload

- Bridging Mode
	- Listener is configured for HTTPS
	- Connection is terminated on the ELB
	- ELB needs a cert for the domain name
		- Cert is stored on the ELB itself; risky
	- Ideal for strong security
	- ELB initiates new SSL connection for backend instances
		- Instances need SSL certs and compute for cryptographic operations
- Pass-through Mode
	- NLB passes connection to instances
	- Each instance must have SSL cert installed
	- No cert exposure to AWS, everything is self-managed and secure
		- No enceryption or decryption happens on the NLB itself
	- Listener is configured for TCP
- SSL Offload Mode
	- Listener is configured for HTTPS
	- Connections are terminated, ELB then connects to backend using HTTP
		- No cert or cryptographic requirements
		- Data is sent in plaintext over AWS

## Connection Stickiness

- Without stickiness:
	- Connections are distributed across all in-service backend instances
	- Unless application handles user state, this could cause user logoffs, shopping cart losses, etc
	- Not ideal for stateful apps
- With stickiness:
	- User connection request to ELB generates a cookie
		- Cookie locks the end user device to a single backend instance for a duration
		- Cookie is called `AWSALB`
		- Cookie duration lasts between 1sec and 7 days
	- End user will connect to a different instance only if:
		- Instance fails
		- Cookie expires
	- Can cause uneven load on backend servers/instances
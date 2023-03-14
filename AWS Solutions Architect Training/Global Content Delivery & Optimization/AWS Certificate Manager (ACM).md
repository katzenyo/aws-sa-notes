>[!Warning] On the Exam
> - With ACM-generated certs, ACM automatically renews them
> - If imported, you are responsible for renewal
> - Certs can be deployed to supported services
> 	- Supports AWS services only (CloudFront, Load Balancers, and API Gateway, **NOT EC2**)
> - Regional service
> 	- Certs cannot leave the region after generated/imported
> 	- ***To use a cert with a load balancer in a specific region, the cert in ACM must also be in the same exact region***
> 	- Global services (such as CloudFront) must always use us-east-1

- HTTP - simple but insecure
- HTTPS
	- SSL/TLS layer of encryption for HTTP
	- Data is encrypted in transit
	- Certs prove identity
		- Chain of trust - signed by a trusted authority
- ACM allows you to run a public or private Certificate Authority (CA)
- Private CA - apps need to trust your private CA
- Public CA - browsers trust a list of providers, which trust other providers
- ACM can generate or import certs

## Architecture

![[Pasted image 20230311135446.png]]
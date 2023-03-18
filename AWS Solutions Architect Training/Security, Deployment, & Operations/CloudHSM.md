>[!Warning] On the Exam
> - True single tenant hardware security module (HSM)
> - Fully FIPS 140-2 Level 3 compliant (KMS is Level 2, some Level 3 compliance)
> 	- If something requires Level 3 compliance, you need an HSM (either cloud or on prem)
> - Access via industry standard APIs
> 	- PKCS#11
> 	- Java Cryptography Extensions (JCE)
> 	- Microsoft CryptoNG (CNG) libraries

## Vs KMS

- With KMS, AWS managed, shared but separated
- AWS provisioned, but fully customer managed
- KMS can use CloudHSM as a custom key store (CloudHSM integration with KMS)

## Architecture

>[!Important]
> - Not HA by default
> 	- Must deploy multiple CloudHSMs and configure them as a cluster
> 	- Must have one cluster in each AZ being used

![[Pasted image 20230318150644.png]]

## Use Cases

>[!Warning] On the Exam
> - No native AWS integration with AWS products
> 	- Cannot be accessed via AWS APIs
> - Offloading SSL/TLS processing for web servers
> - Enables transparent data encryption (TDE) for Oracle Databases
> - Protecting private keys for an issuing Certificate Authority
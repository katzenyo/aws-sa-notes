
- Cognito has awful naming schema
- Authentication, Authorization, and user mgmt for web/mobile apps
- USER POOLS
	- For sign-in and getting a JSON Web Token (JWT)
	- Most AWS services can't use JWTs
	- User directory mgmt and profiles, sign up/sign-in (customizable web UI), MFA, and other security features
- IDENTITY POOL
	- Offer access to Temporary AWS creds
	- Unauthenticated Identities
		- Guest users
	- Federated Identities
		- Google, Facebook, SAML 2.0, & user pool for short term AWS creds

## User Pools

![[Pasted image 20230310151248.png]]

## Identity Pools

![[Pasted image 20230310151450.png]]

## User & Identity Pools Together

![[Pasted image 20230310151616.png]]


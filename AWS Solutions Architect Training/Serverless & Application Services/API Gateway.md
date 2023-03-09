
- Create and manage APIs
- Endpoint/entry point for apps
- Sits between apps & integrations (services)
- HA, scalable, handles authorization, throttling, caching, CORS, transformations, OpenAPI spec, direct integration, and more
- Can connect to services/endpoints in AWS or on prem
- HTTP APIs, REST APIs, WebSocket APIs

## Architecture

![[Pasted image 20230309145347.png]]

## Authentication

![[Pasted image 20230309145531.png]]

## Endpoint Types

- Edge-Optimized
	- Routed to nearest CloudFront POP
- Regional
	- Clients in same region
- Private
	- Accessible only within a VPC via interface endpoint

## Stages

![[Pasted image 20230309145723.png]]

## Errors

> [!Warning] On the Exam

- 4XX
	- Client error
	- Invalid request on client side
	- 400
		- Bad Request
	- 403
		- Access Denied
	- 429
		- API Gateway throttling
- 5XX
	- Server error
	- Valid request, but backend server issue
	- 502
		- Bad Gateway exception
		- bad output returned by Lambda
	- 503
		- Service unavailable
		- Endpoint offline, service issues
	- 504
		- Integration failure/timeout
		- 29s timeout

## Caching

![[Pasted image 20230309150030.png]]
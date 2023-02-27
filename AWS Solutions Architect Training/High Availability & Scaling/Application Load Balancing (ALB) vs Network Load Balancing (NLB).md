
## Load Balancer Consolidation

- Classic Load Balancers (v1 CLBs) don't scale
	- Each unique HTTPS name requires an individual CLB because SNI isn't supported
	- Requires 1 SSL cert for each CLB
- Modern LBs (v2 LBs)
	- Single ELB for multiple HTTPS names
	- Listener Rules allows one SSL cert per rule for the same ELB
	- Use multiple Target Groups that forward connections to multiple Scaling Groups
	- Supports consolidation

## Application Load Balancers (ALB)

- Layer 7 LB
	- listens on HTTP and/or HTTPS
	- L7 content type: cookies, custom headers, user location, app behavior
- No support for other L7 protocols (SMTP, SSH, gaming, etc)
	- No support for TCP/UDP/TLS listeners
- HTTP/HTTPS (SSL/TLS) always terminated on the ALB
	- No support for end-to-end, unbroken SSL connections
	- New secure connection must made to the app
	- All ALBs must have SSL certs if HTTPS is used
- Slower than NLB
	- More levels of network stack to the process
- Health checks evaluate app health

### Rules

>[!Warning] On the Exam
> - If required to forward encrypted connections to instances without terminating the connections, then a Network Load Balancer **must** be used instead!

- Direct connections which arrive at a listener
- Processed in a priority order
- Default rule = catchall
- Rule Conditions
	- `host-header`
	- `http-header`
	- `http-request-method`
	- `path-pattern`
	- `query-string`
	- `source-ip`
- Actions
	- forward
	- redirecft
	- fixed-response
	- authenticate-oidc
	- authenticate-cognito

## Network Load Balancer (NLB)

>[!Warning] On the Exam
> - For questions that talk about things that aren't web or secure web (HTTP/S), default to NLBs
> - End-to-end encryption: NLBs and TCP listeners
> - Used with private link to provide services to other VPCs

- Layer 4 LB
	- TCP, TLS, UDP, TCP_UDP
- No visibility/understanding of HTTP/HTTPS
	- Can't interpret headers, cookies, or session stickiness
- Incredibly fast
	- Millions of requests per second, 25% of ALB latency
	- Ideal for SMTP, SSH, game servers, financial apps (not https)
- Health checks only check ICMP/TCP handshake
	- Not app aware
- NLBs can have static IPs
	- Useful for whitelisting, strict security environments
- Forward TCP to instances
	- Unbroken, end-to-end encryption connections

## ALB vs NLB

>[!Warning] On the Exam
> - Use [[Application Load Balancing (ALB) vs Network Load Balancing (NLB)#Network Load Balancer (NLB)|NLBs]] for:
> 	- Unbroken, end to end encryption
> 	- Static IP for whitelisting
> 	- Fastest performance (millions of requests per second (rps))
> 	- Protocols that are not HTTP/HTTPS
> 	- Privatelink
> - Otherwise, use [[Application Load Balancing (ALB) vs Network Load Balancing (NLB)#Application Load Balancers (ALB)|ALBs]]
>[!Warning] On the Exam
> - Every "connection" contains two parts: request and response

## Stateless Firewalls

- Doesn't understand the state of connections
- Two rules: one inbound, one outbound
- Any servers accepting and initiating connections (e.g. web servers), two rules required for each request/response and they must be the inverse of the request
- Request component is always going to be a well-known port
	- Stateless firewalls remember response ephemeral ports, not the well known port

## Stateful Firewalls

>[!Warning] On the Exam
> - Stateful means lower admin overhead

- Intelligent enough to identify request and response components of a connection as being related
- Allowing request (inbound or outbound), means response is automatically allowed
>[!Warning] On the Exam
> - Aware of the Layer 7 protocol (http)
> - Can identify normal/abnormal requests, protocol specific attacks
> - Encryption (HTTPS) is termianted (decrypted) on the L7 firewall
> - New encrypted L7 connection between firewall and backend
> - Data at L7 can be inspected, blocked, replaced, or tagged
> 	- Able to identify, block, and adjust specific apps (such as Facebook)
> - Keeps all L3, L4, and L5 features but can react to L7 elements
> 	- DNS, RATE, Content, Headers, etc

## Architecture

### Normal Firewalls ([[Network Starter Pack#Layer 3 Routers/devices|Layer 3]]/[[Network Starter Pack#Layer 4 - Transport|4]]/5)

>[!Warning] On the Exam
> - Layer 3 and 4
> 	- Packets and segments, request and response are different and unrelated
> 	- Does not understand sessions
> 	- 'Understands' layers 1-4
> - Layer 5 (session)
> 	- 'Understands' the concept of sessions
> 	- Request and response can be considered part of a single session
> 	- Reduced admin overhead, allows for more contextual security
> 	- Understands Layers 3/4 plus 5

- No visibility into Layer 7

![[Pasted image 20230318125445.png]]

### Application (Layer 7) Firewalls

![[Pasted image 20230318125759.png]]
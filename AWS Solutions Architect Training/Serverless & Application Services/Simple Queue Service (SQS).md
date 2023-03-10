
- Publicy, fully managed, HA message queues
	- Standard or FIFO (first in first out)
		- Standard
			- Guarantee at least once delivery
		- FIFO
			- Guarantee exactly once delivery
			- Performance: 3000 msgs per second with batching, up to 300 per second without
		- Billed based on requests
		- 1 request = 1-10 msgs up to 64KB total
		- Short polling (immediate) vs Long polling (`waitTimeSeconds`, up to 20s)
			- Use Long polling by default
		- Encryption at rest ([[Key Management Service|KMS]]) & in transit
		- Queue policies control access to queues
- Messages up to 256KB in size
	- Use links instead for large data
- Received messages are hidden
	- `VisibilityTimeout`: amount of time a message is hidden after it's received
	- Either reappears (retry) or are deleted after timeout
- Dead-Letter queues
	- Used for problem/corrupt messages
- [[Auto Scaling Groups|ASGs]] can scale and [[AWS Lambda|Lambdas]] invoke based on queue length

## Architecture

![[Pasted image 20230309160450.png]]

## SNS and SQS Fanout

>[!Warning] On the Exam
> - Memorize this architecture (???)

![[Pasted image 20230309160621.png]]


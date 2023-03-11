>[!Warning] On the Exam
> - Use SNS or SQS by default for most **new** implementations
> 	- If you require queues or topics
> 	- If AWS integration is required (logging, permissions, encryption, service integration)
> - Use AmazonMQ
> 	- If you need to migrate from an existing system with little to no app changes
> 	- If APIs such as JMS or protocols such as AMQP, MQTT, OpenWire, or STOMP are required
> 	- **NOT A PUBLIC SERVICE**
> 		- **REQUIRES PRIVATE NETWORKING**

## Preface

- SNS and SQS are AWS services using AWS APIs
- SNS provides Topics and SQS provides Queues
- Public Services
	- highly scalable
	- AWS integrated
- Many orgs may already use topics and queues and want to migrate into AWS
	- SNS and SQS won't work out of the box
	- MQ provides a standards compliant solution for migration

## MQ Overview

- Open source message broker
- Based on managed Apache ActiveMQ
	- Uses JMS API
	- If you need protocols such as AMQP, MQTT, OpenWire, and STOMP, use MQ
- Provides queues and topics
- One to one or one to many
- Single instance (test, dev, cheap) or HA Pair (active/standby)
- VPC based (not a public service)
	- Private networking required
- Now AWS native integration
	- Delivers ActiveMQ product which you manage

## Architecture

![[Pasted image 20230311102000.png]]



## Design Limitations of Lambda

- Lambda is FaaS (Function as a Service)
- 15-minute execution time limit
	- Lambda functions can be chained together, but it gets messy at scale
- Runtime environments are stateless

## State Machine

- Essentially a serverless workflow
	- Start > states > end
- State are things that occur
- Maximum duration: 1 year
- Standard workflow and Express workflow
- Started via API Gateway, IOT Rules, EventBridge, Lambda, manually
- Amazon States Language (ASL)
	- JSON template
- [[IAM Roles]] used for permissions

### States

- SUCCEED & FAIL states
- WAIT state
- CHOICE state
- PARALLEL state
- MAP state
- TASK state
	- Can be used by Lambda, Batch, DynamoDB, ECS, SNS, SQS, Glue, SageMaker, EMR, Step Functions

## Step Functions

![[Pasted image 20230309144540.png]]
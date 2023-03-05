>[!Warning] On the Exam
> - 900s (15min) function timeout
> 	- Any code that takes longer than 15 min to run can't be used with Lambda

- Function-as-a-Service (Faas) - short running & focused
- Lambda function
	- Piece of code lambda runs
- Functions use a runtime (e.g. Python 3.8)
- Functions are loaded and run in a runtime environment
- Environment has a direct memory (indirect CPU) allocation
- Billed for the duration that a function runs
- Key part of serverless architectures
- If Docker is mentioned, it means "not Lambda"

## Architecture

![[Pasted image 20230304192337.png]]

## Common Uses

- Serverless apps (S3, API Gateway, Lambda)
- File Processing (S3, S3 Events, Lambda)
- Database Triggers (DynamoDB, Streams, Lambda)
- Serverless CRON (EventBridge/CWEvents + Lambda)
- Realtime Stream Data Processing (Kinesis + Lambda)

## Lambda Networking

### Public Lambda (default)

- Lambda functions are public by default
	- Can access both public AWS services and the internet 
- No access to VPC-based services
	- Unless public IPs are provided and security controls allowing access are implemented
- Offers the best performance since it lacks specific VPC networking requirements

![[Pasted image 20230304193622.png]]


### VPC Networking

- Lambda functions running in a VPC obey all VPC networking rules
	- Can't access things outside the VPC without specific networking rules allowing external access
	- Can use VPC endpoints to provide access to public AWS services
	- Or use Nat gateway and internet gateway to access internet

![[Pasted image 20230304214628.png]]

## Security

- Lambda execution roles are IAM roles attached to lambda functions
	- They control the permissions the lambda function receives
- Lambda resource policies control what services/accounts can invoke lambda functions

![[Pasted image 20230304215031.png]]

## Logging

- Lambda uses [[CloudWatch Basics|CloudWatch]], [[CloudWatch Logs]], and X-Ray
- Logs from Lambda executions - CloudWatch Logs
- Metrics
	- Invocation success/failure, retries, latency, stored in CloudWatch
- Lambda can be integrated with X-ray for distributed tracing
- **CloudWatch Logs require permisisons via Execution Role**

## Invocation

### Synchronous Invocation

>[!Warning] On the Exam
> - Response result (success or failure) is returned during the request
> - Errors and retries have to be handled within the client

- CLI/API invokes lambda function, passing in data and waiting for a response
- Lambda function responds with data or fails

![[Pasted image 20230304221536.png]]

### Asynchronous Invocation

>[!Warning] On the Exam
> - Lambda function needs to be idempotent
> 	- Reprocessing a result should produce the same end state
> - Events can be sent to dead letter queues after repeated failed processing
> - Lambda supports destinations where successful or failed events can be sent
> 	- SQS, SNS, Lambda, and EventBridge

- Used when AWS services invoke Lambda functions

![[Pasted image 20230304223028.png]]

### Event Source Mappings

>[!Warning] On the Exam
> - Typically used on streams or queues which don't support event generation to invoke lambda
> 	- Kinesis, DynamoDB streams, SQS
> - Permissions from the lambda execution role are used by the Event Source Mapping to interact with the event source
> - SQS Queues or SNS topics can be used for any discarded, failed event batches

## Versions

- Lambda functions have versions (v1,v2,v3, etc)
- Versions are the code + configuration of the lambda function
- Versions are immutable
	- They never change once published and possess their own ARN
- `$Latest` points at the latest lambda version
- Aliases (DEV, STAGE, PROD) can point at a version
	- They can be changed

## Startup Times

>[!Warning] On the Exam
> - Lambda invocation can reuse an execution context, but has to assume it can't
> 	- If used infrequently, contexts are removed
> 	- Concurrent executions will use multiple (potentially new) contexts
> - *Provisioned Concurrency*
> 	- AWS creates and keeps *x* number of onctexts warm and ready to use
> 	- Improves startup times

- *Execution context* is the environment a lambda function runs in
- *Cold start*: full creation and configuration time including function code download
	- ~100ms time
- *Warm start*
	- Same execution context is reused
	- New event is passed in but execution context creation can be skipped
	- ~1-2ms time
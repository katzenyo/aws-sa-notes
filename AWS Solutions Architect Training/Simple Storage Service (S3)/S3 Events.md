>[!Warning] Exam PowerUp
> - Events can be triggered for Object Restores (S3 Glacier, Glacier Deep Archive)
> 	- Post (initiated), completed
> - Replication (OperationMissedThreshold, OperationReplicatedAfterThreshold, OperationNotTracked, OperationFailedReplication)

- Notifications generated when events occur in a bucket
	- Can be delievered to SNS, SQS, and Lambda
- Object Created (put,post,copy, completedmultipartupload)
- EventBridge is newer, more supported, will deprecate Event Notifications

## Notification Workflow

1. Configure Event Notification policy
2. Apply policy to bucket
3. Bucket generates events (create, delete, restore, replicate)
4. Events interact with services (Lambda, SQS Queue, SNS Topic)
	1. Services require Resource Policies allowing S3 services to interact with them
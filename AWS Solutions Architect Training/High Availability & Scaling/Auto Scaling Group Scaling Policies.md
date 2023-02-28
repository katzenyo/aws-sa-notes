- ASG's can be created without scaling policies
- Manual scaling
	- Adjusting min, max, & desired
	- Useful for testing and urgent cases
- Simple Scaling
	- Inflexible, inefficient
- Step Scaling - AWS recommended over Simple
	- Vary based on level of alarm breach (upper, lower bounds configured)
- Target Tracking
	- Tracks a metric, auto scales up/down based on target metric
- Scaling based on SQS
	- ApproximateNumberOfMessagesVisible

## Simple Scaling

![[Pasted image 20230227195715.png]]

## Step Scaling

![[Pasted image 20230227195925.png]]
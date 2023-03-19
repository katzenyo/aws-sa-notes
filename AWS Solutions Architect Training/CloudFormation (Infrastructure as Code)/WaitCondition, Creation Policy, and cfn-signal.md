
## Signal

- Configure CloudFormation to hold
- Wait for *x* # of success signals
- Wait for timeout h:m:s for signals (12 hour max)
- If success signals are received, status changes to `CREATE_COMPLETE`
- If failure signal received, creation fails
	- If timeout is reached, creation fails
- CreationPolicy or WaitCondition

## Creation Policy

![[Pasted image 20230319155357.png]]

## WaitCondition

![[Pasted image 20230319155602.png]]
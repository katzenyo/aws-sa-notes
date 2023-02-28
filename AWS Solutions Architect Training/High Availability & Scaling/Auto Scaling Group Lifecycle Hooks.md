- Custom Actions on instances during ASG actions
	- Instance launch/terminate transitions
- Instances are paused within the flow until a timeout
	- Either continues or abandons action after timeout
	- Or ASG process `CompleteLifecycleAction` is resumed
- EventBridge or SNS notifications

## Architecture

![[Pasted image 20230227203021.png]]
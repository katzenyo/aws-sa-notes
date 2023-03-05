
## Key Concepts

- If *x* happens - or *y* times - do *z*
- EventBridge is a better version of CloudWatch
- Default event bus for the account
	- CloudWatch Events has only one implicit bus, not exposed in UI
	- EventBridge can have multiple event busses
	- Rules match incoming events or schedules
- Route events to one or more targets (such as Lambda)

## Architecture

![[Pasted image 20230305001401.png]]
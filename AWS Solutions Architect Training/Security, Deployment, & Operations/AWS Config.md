
- Records configuration changes over time on resources
- Ideal for auditing changes, compliance with standards
- Does not prevent changes from happening, simply checks compliance
- Regional Service
	- Monitors particular regions
	- Supports cross-region and cross-account behavior
- Changes can generate [[Simple Notification Service (SNS)|SNS notifications]] and near realtime events via [[CloudWatch Events and EventBridge|EventBridge]] and [[AWS Lambda|Lambda]]

## Architecture

- Optional features on left (green), mandatory features on right (red)

![[Pasted image 20230318152217.png]]
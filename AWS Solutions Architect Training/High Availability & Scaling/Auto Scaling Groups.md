>[!Warning] On the Exam
> - Autoscaling Groups are FREE
> - Only created resources are billed
> - Use cooldowns to avoid rapid scaling
> - Use more, smaller instances (granularity) to control costs
> - Use with [[Application Load Balancing (ALB) vs Network Load Balancing (NLB)#Application Load Balancers (ALB)|ALB's]] for elasticity (abstraction)
> - ASG defines WHEN and WHERE
> 	- [[Launch Configuration & Launch Templates|Launch Templates]] define WHAT

- Automatic Scaling and Self-healing for EC2
	- [Scale In Order](https://docs.aws.amazon.com/autoscaling/ec2/userguide/as-instance-termination.html#common-scenarios-termination-scale-in):
		1. Terminates instances with oldest launch configuration
		2. Then, terminates instances closest to next billing hour
		3. Finally, an instance is chosen at random
- Uses [[Launch Configuration & Launch Templates|Launch Templates or Launch Configurations]]
- Minimum, Desired, and Maximum sizes
	- e.g. 1:2:4 (min:desired:max)
- Keep running instances at the desired capacity by provisioning or terminating instances
- Scaling Policies automate based on metrics

## Architecture

![[Pasted image 20230227180501.png]]
![[Pasted image 20230227180539.png]]

## [[Auto Scaling Group Scaling Policies|Scaling Policies]]

- Manual Scaling
	- Manually adjust desired capacity
- Scheduled Scaling
	- Time-based adjustment, e.g. sales
	- For known periods of usage
- Dynamic Scaling
	- Simple scaling
		- e.g. CPU above 50% then add an instance
	- Stepped Scaling
		- Bigger increase/decrease based on difference
	- Target Tracking
		- Auto scales based on desired target, e.g. CPU usage
- Cooldown Periods
	- Value in seconds, how long to wait to perform the next scaling action

## [[Auto Scaling Group Health Checks|Health]]

- Auto Scaling Groups also monitor health
- If instance fails, ASG terminates and replaces the instance with a new one

## ASG + Load Balancer

![[Pasted image 20230227181617.png]]

## Scaling Processes

- Launch and Terminate
	- Suspend and Resume
- AddToLoadBalancer
	- Add to LB on launch
- AlarmNotification
	- Accept notification from CW
- AZRebalance
	- Balanaces instances evenly across all AZs
- HealthCheck
	- Instance health checks on/off
- ReplaceUnhealthy
	- Terminate unhealthy and replace
- ScheduledActions
	- Scheduled on/off
- Standby
	- Use for instances InService vs Standby
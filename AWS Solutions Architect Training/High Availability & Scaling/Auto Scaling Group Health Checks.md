>[!Warning] On the Exam
> - If an auto scaling group is continuously provisioning and terminating instances, it's likely the result of not a long enough health check grace period to allow time for system launch, bootstrapping, or app startup

- EC2 (default), ELB (can be enabled), & custom
- EC2
	- Stopping, Stopped, Terminated, Shutting Down or Impaired (anything but 2/2 Status Checks Passed) = Unhealthy state
- ELB - Healthy = Running & passing ELB health check
	- Can be more application aware (Layer 7)
- Custom
	- Instances marked healthy or unhealthy by an external system/tool
- Health check grace period
	- This is a time delay before starting health checks
	- Default is 300s
	- Allows time for system launch, bootstrapping, and application start
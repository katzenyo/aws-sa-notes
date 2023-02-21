>[!Warning] On the Exam
> - Use for configuring active-passive failover in Route 53
> 	- Route traffic to primary resource when healthy
> 	- Route traffic to secondary resource when primary resource fails health checks

- Common architecture is to use failover for "out of band" failure or maintenance page for a service (e.g. EC2/S3)
- If health check target is Healthy, the primary record is returned
- If primary health check fails, secondary (failover) record is returned
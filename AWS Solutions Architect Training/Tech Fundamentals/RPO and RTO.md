>[!Abstract]
> worst case = time between backups
> more frequent backups = more cost = lower RPO
> reduce RTO via planning, monitoring, notifications, process, spare hardware, training, and more efficient systems (e.g. cloud)
> RPO/RTO varies between businesses
> aim for the best possible requirements balanced against cost

>[!Definition] Recovery Point Objective (RPO)
>Maximum amount of data (time) that can be lost during a DR situation before loss exceeds what the organization can tolerate.

- Data Recovery Point: last successful backup or chain of backups
- Lower RPO = more frequent backups = higher cost

>[!Definition] Recovery Time Objective (RTO)
>Maximum tolerable length time that a system can be down, end-to-end, after a failure occurs

- Recovery Time begins at the moment of failure and ends when system is operational and returned to the business

>[!Warning] Factors Affecting RTO
> - How long until an issue is known?
> - Is there monitoring?
> 	- Is it reliable?
> 	- How does it work?
> 	- Does it notify the correct people?
> - What is the issue?
> 	- Can it be fixed quickly?
> - What kind of backup?
> 	- Where is it?
> 	- Who's responsible for restoring it?
> 		- Are they available?
> 	- How is it restored?
> 	- Is the DR process documented?
> - Is testing process completed?
> 	- Business Testing
> 	- User Testing
> 	- Final handover





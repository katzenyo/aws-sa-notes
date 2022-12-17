## High Availability

>[!Abstract] HA
> - Aims to ensure an agreed level of operational performance, usually uptime, for a higher than normal period
> - A system that is online and providing services for as long as possible
> - Minimizing outages

## Fault Tolerance

>[!Abstract] FT
> - The property that enables a system to continue operating properly in the event of a failure of some of its components
> - Fault tolerant systems are designed to work *through* failure, with *no disruption*
> - Much more expensive, difficult to implement

## Disaster Recovery

>[!Abstract] DR
> - A set of policies, tools, and procedures to enable the recovery or continuation of vital tech infrastructure/systems in the aftermath of a disaster (natural or human-caused)
> - How to recover when HA and FT fail

- Pre-planning
	- Backups
	- Offsite
		- Hot site
		- Cold site
	- Resilience/redundancy (AWS)
- DR Process
	- Logins, processes, knowledge, etc must be ready to go at offsite
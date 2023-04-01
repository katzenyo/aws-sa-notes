>[!Warning] On the Exam
> - If NoSQL is mentioned on exam questions
> 	- Prioritize DynamoDB answers
> - If relational database is mentioned on exam questions
> 	- AVOID DynamoDB
> - Key/Value questions on exam
> 	- Prioritize DynamoDB
> - Access via console, CLI, API, or No SQL
> 	- Excludes DynamoDB (generally)
> - Billing based RCU, WCU, Storage, and features
> 	- Only pay for storage consumede

- NoSQL public database as a service
	- [[Database Refresher & Models#Key-Value Databases|Key/Value store]]
	- [[Database Refresher & Models#Document Database|Document store]]
- No self managed servers or infrastructure
- Manual/automatic provisioned performance in/out or on-demand
- AZ resilient and optionally global resilience
- Single digit millisecond access (SSD)
- Backups, point in time recovery, encryption at rest
- Event-driven integration (do things when data changes)
- Cardinality
	- High cardinality: more distinct partition key values
		- Spreads more requests over a partitioned space
	- Low cardinality: fewer distinct partition key values

## Tables

![[Pasted image 20230322152521.png]]

## On-Demand Backups

- Full copy of table is made
	- Retained until removed
- Restores
	- Can be restored into the same or cross-region
	- WIth or without indexes
	- Can adjust encryption settings

## Point-in-time-Recovery (PITR)

- Must be enabled manually
- Continuous record of changes allows replay to any point in the window
	- 35-day recovery window
	- 1-second granularity


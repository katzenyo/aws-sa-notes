
- ACID, BASE: database transaction models
- CAP Theorem
	- Consistency, Availability, Partition Tolerance (resilience)
		- Choose 2
			- More than two can't be selected: either must continue the read operation and maintain availability at the risk of consistency, or drop the read operation and sacrifice availability for consistency
		- Consistency
			- every read operation receives the most recent write operation
		- Availability
			- every request will receive a non error response but without guaranteeing the most recent write
		- Partition Tolerance
			- System can be made of multiple network partitions
			- Partitions allow system to operate even if dropped messages or errors between nodes
	- ACID = consistency
	- BASE = availability

## ACID

>[!Warning] On the Exam
> - If ACID is mentioned on the exam, it almost always refers to RDS
> - Limits ability to scale

- Atomic
	- All parts of a transaction succeed or none of them succeed
- Consistent
	- Transactions move database from one valid state to another
	- There is no in-between state allowed
- Isolated
	- If multiple transactions occur simultaneously, they don't interfere with each other
	- Each transaction executes as if it's the only transaction
- Durable
	- Transactions are stored on non-volatile memory
	- Resilient to power outages and crashes

## BASE

>[!Warning] On the Exam
> - If BASE is mentioned, it means a noSQL style database
> - If noSQL or DynamoDB are mentioned with ACID, it refers to DynamoDB transactions

- Basically Available
	- Read/write operations are available as much as possible
	- Lacks consistency guarantees
- Soft State
	- Database doesn't enforce consistency
	- Consistency is offloaded onto the application or user
- Eventually Consistent
	- Doesn't enforce immediate consistency
	- Consistency will happen after a certain amount of time
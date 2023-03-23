>[!Warning] On the Exam
> - Careful with projection consumed capacity
> - Queries on attributes not projected are expensive
> - Use GSI as default
> 	- Use LSI only when strong consistency is required
> - Use indexes for *alternative access patterns*
> 	- If seeing the data from a different perspective is necessary

## Indexes

>[!Warning] On the Exam
> - Query only works on 1 partition key value at a time
> - Local Secondary Index (LSI)
> 	- Allows viewing with different sort key, but same partition key
> - Global Secondary Index (GSI)
> 	- Allows viewing with both different partition key and sort key
> - Can choose which attributes from base table can be projected
> 	- Affects index efficiency

- Most efficient operation in DynamoDB
- Indexes are alternative views on a table

## Local Secondary Index (LSI)

>[!Warning] On the Exam
> - They must be created along with a table
> 	- Cannot be created after a table has already been created
> - Provide different sort key, but same partition key
> - Shares RCU and WCU with table

- An alternative view for a table
- Attributes
	- ALL
	- KEYS_ONLY
	- INCLUDE

![[Pasted image 20230322165724.png]]

## Global Secondary Index (GSI)

>[!Warning] On the Exam
> - Can be created at any time
> - Default limit of 20 per base table
> - Alternative partition key and sort key
> - Have their own RCU and WCU allocations, separate from base table
> - Always eventually consistent
> 	- Replication between base table and GSI is asynchronous

- Attributes (same as LSI)
	- ALL
	- KEYS_ONLY
	- INCLUDE
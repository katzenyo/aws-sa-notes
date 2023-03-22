
## Reading and Writing

>[!Warning] On the Exam
> - Every operation consumes at least 1 RCU/WCU
> 	- 1 RCU: 1x4KB read op per second
> 	- 1 WCU: 1x1KB write op per second

- On Demand
	- For unknown, unpredictable loads, and low admin overhead
	- Price per million read/write units
- Provisioned
	- RCU and WCU set on a per table basis
- Every table has a RCU/WCU burst pool (300 seconds)
	- Throttling if capacity settings exceeded

## Query Operation

- Queries accept a single primary key value and optionally a secondary key or a range of keys
- Capacity consumed is the size of all returned items combined
	- Always more efficient to return multiple items in a single operation
- Filtering discards, but the capacity is still consumed regardless
- Can only query on PK, *or* PK and SK

![[Pasted image 20230322161953.png]]

## Scan Operation

- Least efficient operation but most flexible
- Moves through a table consuming the capacity of every item
- Allows complete control on what data is selected
	- Any attributes can be used and any filters applied, but consumes capacity for every item scanned

![[Pasted image 20230322161937.png]]

## Consistency Models

- *Storage Node*: where DynamoDB stores replicas of the database in each AZ

- Eventually Consistent
	- 50% consumption rate of strongly consistent
	- Easier to implement, scales better
- Immediately/Strongly Consistent
	- More costly, scales less well

![[Pasted image 20230322162922.png]]

## [WCU Calculation](https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/ProvisionedThroughput.html#ItemSizeCalculations.Writes)

- Store 10 items per second = 2.5K average size per item
- Calculate WCU per item
	- Divide by WCU size (1k), round up to next whole number (3)
	- Multiply by average number per second (30)
	- WCU required = 30

## [RCU Calculation](https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/ProvisionedThroughput.html#ProvisionedThroughput.CapacityUnits.Read)

- Retrieve 10 items per second = 2.5k average size
- Calculate RCU per item
	- Round up (item size divided by 4kb)
	- Multiply by average read ops per second (10)
	- Strongly Consistent RCU = 10 units
	- Eventually Consistent RCU = 5 units
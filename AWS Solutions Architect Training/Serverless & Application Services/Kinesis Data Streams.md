
- Scalable streaming service (ingest data)
- Producers send data into Kinesis stream
- Streams can scale from low to near infinite data rates
- [[AWS Public vs Private Services|Public service]], HA by design
- Data is stored for a 24-hour period window
	- Storage time/window can be increased to max of 365 days (at addl cost)
- Multiple consumers access data during the moving window
- Uses shard architecture
	- Kinesis Data Record (1MB size)

## Architecture

![[Pasted image 20230309184259.png]]

## [[Simple Queue Service (SQS)|SQS]] vs Kinesis

- Is question about ingestion of data or async communications?
- SQS
	- has 1 production group, 1 consumption group
	- for decoupling and async communications
	- has no persistence, no time window
- Kinesis
	- Designed for huge scale data ingestion
	- Multiple consumers, rolling availability window
	- Data ingestion, Analytics, Monitoring, app clicks
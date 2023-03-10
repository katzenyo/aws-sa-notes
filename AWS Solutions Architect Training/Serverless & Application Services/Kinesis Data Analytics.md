
- Real time processing of data using SQL
- Ingests from [[Kinesis Data Streams]] or [[Kinesis Data Firehose]]
- Supports destinations to Firehose (S3, Redshift, ElasticSearch, Splunk), AWS, and Kinesis Data Streams

## Architecture

![[Pasted image 20230310144258.png]]

## When to Use

- Streaming data that requires real-time SQL processing
	- Time-series analytics
		- Elections/e-sports
	- Real-time dashboards
		- Leaderboards for games
	- real-time metrics
		- Security & response teams
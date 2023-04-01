
- Serverless ETL (Extract, Transform, Load)
	- compared to datapipeline (which can do ETL) and uses servers (EMR)
- Moves and transforms data between src and dst
- Crawls data sources and generates AWS Glue Data catalog
- Data sources
	- Stores: S3, RDS, JDBC Compatible & DynamoDB
	- Streams: [[Kinesis Data Streams]] & Apache Kafka
	- Data Targets: S3, RDS, JDBC databases
- Ideal for:
	- Analyzing and categorizing data

## Data Catalog

- Collection of persistent metadata about data sources in a region
- One catalog per region per catalog
	- Avoids data silos
- Amazon Athena, Redshift Spectrum, EMR & AWS Lake Formation all use Data Catalog
	- configure *crawlers* for data sources

## Architecture

![[Pasted image 20230310152118.png]]
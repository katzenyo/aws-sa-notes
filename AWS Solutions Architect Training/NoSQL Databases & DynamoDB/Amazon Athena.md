>[!Warning] On the Exam
> - No data structure
> - Ideal for:
> 	- Queries where loading/transformation isn't desired
> 	- Occasional/ad-hoc queries on data in S3
> 	- Serverless querying scenarios
> 		- Cost consciousness
> 	- Querying AWS logs
> 		- VPC flow logs, CloudTrail, ELB logs, cost reports, etc
> 	- AWS Glue Data Catalog & Web Server Logs
> 	- Used with Athena Federated Query (other data sources)

- Serverless interactive querying service
- Ad-hoc queries on data
	- Pay only data consumed
	- No base monthly cost
- Schema on read
	- Table-like translation
- Original data is never changed
	- Remains on S3
- Schema translates data
	- Relational-like when read
- Output can be sent to other AWS services

## Architecture

![[Pasted image 20230323010445.png]]
## Key Facts

> [!Warning] On the Exam
> - Fully managed DB Proxy for RDS/Aurora
>	 - Auto scaling and highly available by default
> - Provides connection pooling
>	- Reduces DB Load by pooling connections
>	- Usees multiplexing to distribute connections
> - Only accessible via VPC
> - Accessed via Proxy Endpoint
> - Can enforce SSL/TLS
> - Reduce failover time by over 60%
> - Abstracts DB failure away from your apps

## Why Use RDS Proxy?

- Opening and closing connections consume resources
	- Takes time, creates latency
- With serverless, every lambda function opens and closes
- Handling failure of DB instances is hard
	- Doing it within application adds risk
- DB proxies help, but managing them is non-trivial
	- Scaling, adding resilience is difficult
- Applications connect to Proxy, which pools connections, which connects to the database

## Architecture

>[!Warning] On the Exam
> - RDS Proxy maintains a long-term connection pool
> - Each Lambda function connects to the Proxy
> 	- Faster than connecting directly to DB
> - Client -> proxy connection is established
> 	- Waits even if target DB is non-responsive
> - Abstracts client away from DB failure/failover events
> - RDS Proxy -> DB Instance connections can be reused
> 	- Avoids lag of establishment, usage, and termination for each invocation

![[Pasted image 20230226210757.png]]

## When to Use?

- Experiencing "too many connections" errors
- DB instances using T2/T3 (smaller/burst) instances
- With AWS Lambda
	- Time saved/connection reuse
	- IAM Auth
- Long running connections (SaaS apps) for low latency
- Where resilience to DB failure is a priority
	- RDS proxy can reduce failover time
	- Make it transparent to the application
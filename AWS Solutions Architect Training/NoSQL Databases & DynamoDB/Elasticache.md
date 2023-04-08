>[!Warning] On the Exam
> - Managed Redis or Memcached as a service
> - Can be used to cache data
> 	- For read heavy workloads with low latency reqs
> - Reduces database workloads
> 	- Makes heavy read operations cost effective
> - Can be used to store session data
> 	- Stateless servers
> - Requires application code changes

- In-memory database
	- High performance

## Caching

- In-memory caching allows cost effective scaling of read-heavy workloads
	- Performance improvements at scale

## Session State Data

![[Pasted image 20230323110838.png]]

## Redis vs MemcacheD

### MemcacheD

- Supports simple data structures
- ***No replication***
- Multiple nodes (sharding)
- No backups
- Multi-threaded

### Redis

- Supports advanced structures
- **Multi-AZ replication**
- Replication (scale reads)
- Supports backup & restore
- Transactions
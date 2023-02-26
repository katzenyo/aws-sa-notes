
- Synchronous
	- Means multi-AZ
- Asynchronous
	- Means read replicas

## Performance Improvements

- 5x direct read-replicas per DB instance
- Each providing an additional instance of read performance
- Read-replicas can have read-replicas
	- Lag becomes an issue
- Global performance improvements

## [[RPO and RTO|RPO/RTO]] Improvements

- Snapshots & backups improve RPO
- Doesn't help with RTOs
- Read-replicas
	- almost 0 RPO
	- Can be promoted quickly - low RTO
- Useful for failure only, not data corruption
- Read only, until promoted
- Global availability improvements/global resilience
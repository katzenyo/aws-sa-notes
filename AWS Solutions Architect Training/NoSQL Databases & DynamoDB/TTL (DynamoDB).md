
>[!Warning] On the Exam
> - Timestamp for automatic delete of items

- Specific attribute is selected for TTL
- Per-partition process periodically runs
	- Checks current time (in seconds since epoch) to the value in the TTL attribute
	- Items where TTL attribute is older than current time are set to expired
- Separate per-partition background process scans for expired items
	- Removes them from tables and indexes
	- delete is added to streams if enabled
- DELETE operations caused by TTL are background system processes
	- Don't impact table performance
	- Aren't billable
- Streams of TTL deletions can be enabled
	- 24-hour window
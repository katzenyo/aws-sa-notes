>[!Warning] On the Exam
> - Ideal for simple load balancing or testing new software versions

- hosted zones are given a record weight
- record weight determines distribution/probability of returning that record
	- e.g. a weight of 40 means the record is returned 40% of the time
- Record weight of 0 means a record is never returned
	- If all records are 0, then all records are returned
- If chosen record is Unhealthy, selection process loops until a healthy record is selected
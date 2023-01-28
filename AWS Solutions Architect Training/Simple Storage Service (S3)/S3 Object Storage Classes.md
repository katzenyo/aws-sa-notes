## S3 Standard

>[!Warning] Use Case
> - Use S3 Standard for frequently accessed data which is important and irreplaceable
> - This should be the default storage class unless explicitly determined otherwise

- Default storage class
- Data is replicated across 3 AZs in a single AWS Region
	- MD5 checksums and cyclic redundancy checks (CRCs) to detect, fix data corruption
- HTTP/1.1 200 OK means data is durably stored
- Data is available immediately
	- millisecond first byte latency (objects available in milliseconds)
	- objects can be publicly available
- Nine 9's (99.999999999%) of durability for every 10,000,000 objects (1 object loss per 10,000 years)

### Billing

- Billed gigabyte per month fee for stored data
- Per GB charge for transfer out (transfer in is free)
- Charged per 1,000 requests
- No retrieval fee, minimum duration, or minimum size

## S3 Standard-IA (Infrequent Access)

>[!Warning] Use Case
> - Ideal for infrequent, long-term, and fewer but larger objects (>128KB) that are important/irreplaceable
> - Non-ideal for lots of small files, temporary data, frequently accessed data, or easily-replaced data

- Similar to S3 Standard
- Much more cost-effective due to infrequent access

### Billing

- Similar to S3 standard
- Half as much as S3 standard
- Per request charge & data transfer out cost
- Per GB retrieval fee, cost increases with more frequent data access
- Minimum duration charge of **30 days**
	- objects can be stored for less, but you are billed the minimum duration regardless
	- billed a minimum of 128KB per object

## S3 One Zone-IA (Infrequent Access)

>[!Warning] Use Cases
> - Long-lived, non-critical, replaceable, and infrequently accessed data
> 	- e.g. replica copies or intermediate data

- Only in one AZ, so lacks multi-AZ resiliency of other S3 storage classes

### Billing

- Per GB data retrieval fee, cost increases with frequent access
- Minimum duration charge of 30 days
- Minimum capacity charge of 128KB per object

## S3 Glacier - Instant

>[!Warning] Use Cases
> - Long-lived data accessed once per quarter
> - Millisecond access

- Replicated across three AZ's
- MD5 checksums and cyclic redundancy checks

### Billing

- Per GB retrieval fee, cost increases with frequent access
- Minimum duration charge of 90 days
- Minimum capacity charge of 128KB per object

## S3 Glacier - Flexible

>[!Warning] Use Cases
> - Archival data where frequent or realtime access isn't necessary
> - Minute to hourly retrieval times

>[!Important] For the Exam
> - Objects cannot be made publicly accessible
> - First byte latency = minutes or hours


- Replicated across three AZ's
- Retrieval process required to access data
	- Data is sent to S3 Standard-IA temporarily
	- Retrieval process costs money
	- Retrieval process types
		- Standard (3-5 hours) - `$`
		- Bulk (5-12 hours) - `$$`
		- Expedited (1-5 minutes) - `$$$`

### Billing

- 40kb minimum billable size
- 90-day minimum billable duration

## S3 Glacier Deep Archive

>[!Warning] Use Cases
> - Archival data that is rarely accessed
> - Hours to days for retrieval time
> - e.g. Legal or regulatory storage

>[!Important] For the Exam
> - First byte latency = hours or days

- Cannot be made publicly accessible
- - Retrieval process required to access data
	- Data is sent to S3 Standard-IA temporarily
	- Retrieval process costs money
	- Retrieval process types
		- Standard (12 hours) - `$`
		- Bulk (48 hours) - `$$`
		- Expedited (1-5 minutes) - `$$$`

### Billing

- 40kb minimum billable size
- 180-day minimum billable duration

## S3 Intelligent-Tiering

>[!Warning] On the Exam
> - S3 Intelligent-Tiering should be used for long-lived data with changing or unknown access patterns

- Automatically moves data between tiers via monitoring usage
	- Higher usage items are moved to more frequently accessed tiers
	- Lower usage items moved to more infrequent (colder) tiers

### Tiering structure

>[!Warning] On the Exam
> - Archive Access and Deep Archive tiers are optional


- Frequent Access
	- Billed the same as S3 standard
- Infrequent Access
	- Moved after 30 days of not being accessed
	- Billed the same as Standard-IA
- Archive Instant Access
	- Moved when 90 day access threshold met
	- S3 Glacier Instant Billing
- Archive Access **(Optional)**
	- Moved between 90 and 270 days
	- S3 Glacier Archive Billing
- Deep Archive **(Optional)**
	- Moved between 180 or 730 days
	- S3 Deep Archive Billing

### Billing

- No retrieval fees
- Monitoring and automation cost per 1,000 objects
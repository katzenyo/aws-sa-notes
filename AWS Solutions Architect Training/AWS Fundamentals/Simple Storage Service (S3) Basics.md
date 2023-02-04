>[!Abstract] The Basics
> - Global Storage Platform - regional based/resilient
> 	- Replicated in AZs across the region
> - Public service, unlimited data & multi-user
> - Movies, audio, photos, text, large datasets
> - Economical, accessed via UI/CLI/API/HTTP
> - Default starting point UNLESS  S3 can't deliver solution
> - Objects & Buckets

## Objects

- Two main components
	- Object key (e.g. filename): thing.jpg
		- Identifies object in a bucket
		- Value: data/contents of object
			- Content being stored
			- File size up to 5TB

## Buckets

>[!Abstract] Summary
> - Buckets: 100 soft limit, 1000 hard limit per account
> - Bucket names are globally unique
> - 3-63 characters, all lowercase, no underscores
> - Start with a lowercase letter/number
> - Can't be IP formatted (e.g. 1.1.1.1)
> - Unlimited objects in bucket, 0 bytes to 5TB
> - Key = name, Value = data

>[!Warning] On the Test
> Bucket names are *globally unique* across all accounts and regions

- Created in a specific region
	- Never leaves a region unless configured otherwise
	- Limits failure to a region
- Bucket name
	- globally unique (all accounts and regions)
- Unlimited objects
	- Infinitely scalable
- Flat structure
	- All objects stored at same level
	- Prefixes *appear* as folders but there are no folders/subdirectories/structure

## Patterns & Anti-Patterns

- S3 is an object store: not file or block
- Can't mount an S3 bucket
- Single-user limitation
- Ideal for large scale data storage, distribution, ojr upload
- Great for offloading
- Default input/output to AWS products
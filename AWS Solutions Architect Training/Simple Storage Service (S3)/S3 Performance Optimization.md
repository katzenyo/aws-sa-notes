
## Single PUT Upload

- Single data stream to S3
	- s3:PutObject
- If stream fails, upload fails
	- Entire upload must be started from scratch
- Speed & reliability: limited to 1 stream
	- Non-ideal over long distances
- Limited to 5GB uploads max

## Multipart Upload

- Breaks data into individual parts
	- Minimum size is 100MB
	- Maximum of 10,000 parts
		- Each part can be 5MB to 5GB
	- Last part can be smaller than 5MB
	- Parts can fail but be restarted in isolation
		- Limits risk of transfer
- Transfer rate is much faster due to parallel processing 

## S3 Accelerated Transfer (Off)

- Uses AWS edge locations
- S3 buckets must be enabled manually, disabled by default
	- Restrictions to enable
		- Bucket name can't contain periods
		- Name must be DNS-compatible

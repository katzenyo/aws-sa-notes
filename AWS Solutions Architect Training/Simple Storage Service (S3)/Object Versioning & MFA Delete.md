>[!Important]
>Once versioning is enabled on a bucket, it cannot be disabled
>	- Bucket can instead be suspended

## Versioning

- Without versioning, each object is identified by the unique object key (name)
	- If object is modified, the original version is replaced with the modified version
	- Object id = null
- With versioning, multiple versions of an object can be stored in a bucket
	- Modify operations generate a new version of the object
	- S3 generates an object id
	- When modified, latest version is assigned a new object id
	- Current version is always returned unless specific object id is specified
	- Deleting
		- creates a new version of the object with a delete marker
		- doesn't actually delete the object, simply hides all previous versions
		- Removing the delete marker reveals all versions
		- Full deletion requires specifying an object id

>[!Important] Key Points
> - Versioning cannot be disabled
> - Space is consumed by all versions
> - You are billed for all versions
> - Only way to zero out costs is to delete the bucket

## MFA Delete

- Enabled in versioning configuration
- Requires MFA to change bucket versioning states
- MFA is required to delete versions
- Requires MFA code + code passed with API calls
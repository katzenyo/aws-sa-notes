- Can be enabled on new buckets
	- Can be enabled on existing but only via support request
- Write-Once-Read-Many (WORM) architecture - No deletes, no overwriting
- ***Requires versioning be enabled - individual versions are locked*** 
	- 1- Retention Period
	- 2 - Legal Hold
	- Both, one or the other, or none
	- Settings can overlap
- Bucket can have default Object Lock settings

>[!Warning] On the Exam
> - Legal Holds and Retention Periods are two different things

## Retention Period

- Specify days & years

### Compliance Mode

>[!Warning] On the Exam
>- Retention period must expire before the following can be changed:
> 	- Can't be adjusted, deleted, or overwritten for the duration of retention period
> 	- Retention period can't be reduced during retention period
> 	- Retention mode can't be adjusted during retention period
> 	- Even account root user can't make changes

- Good for medical, financial data, other compliance reasons

### Governance Mode

>[!Warning] On the Exam
> - Special permissions can be granted that allow lock settings to be adjusted
> 	- s3:BypassGovernanceRetention permission
> 	- header must be included: `x-amz-bypass-governance-retention:true` (console UI default)
> - Can be set on objects or as the bucket default
> - Good for:
> 	- Preventing accidental deletion
> 	- Process/governance reasons for keeping object versions
> 	- Test of settings before entering compliance mode

### Legal Holds

>[!Warning] On the Exam
> - Can be set on objects or as the bucket default

- Binary toggle for an object version (on/off)
- No retention
- No deletes or changes until legal hold is removed
- `s3:PutObjectLegalHold` required to add/remove Legal Hold toggle
- Prevents accidental deletion of critical object versions or for legal cases/situations
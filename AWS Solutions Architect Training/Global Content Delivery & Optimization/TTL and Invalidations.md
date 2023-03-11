
## Architecture

![[Pasted image 20230311122133.png]]

## Object Validity

>[!Warning] On the Exam
> - More frequent cache hits = lower origin load
> - Default TTL (behavior) = 24 hour validity period
> - Origin Headers
> 	- `Cache-Control max-age` (seconds)
> 	- `Cache-Control s-maxage` (seconds)
> 	- `Expires` (date & time)
> - Custom Origin or S3 (via object metadata)


- Can set min TTL and max TTL values

## Cache Invalidation

>[!Warning] On the Exam
> - Cache invalidation is performed on a distribution
> 	- Applies to all edge location and takes time
> - Used as a way to correct errors
> - Versioned file names, requires no invalidation
> 	- Points at new object name, bypasses older cached names
> 	- Cost efficacy
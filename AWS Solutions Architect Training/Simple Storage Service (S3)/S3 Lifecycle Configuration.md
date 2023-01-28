- Set of rules that are applied to a bucket
	- Rules consist of actions taken on a bucket or groups of objects
		- Transition Actions
			- Move objects based on time periods
		- Expiration Actions
			- Delete objects based on certain time periods

## Transitions

>[!Warning]
> - S3 One Zone-IA **cannot** transition into Glacier Instant Retrieval
> - Avoid transitioning smaller objects into Standard-IA, Intelligent-Tieiring, or One Zone-IA due to minimum size costs

>[!Important] On the Exam
> - 30-day min period for objects to remain on S3 Standard before transitioning to Standard-IA or One Zone-IA
> - A single rule can't transition to Standard-IA or One Zone-IA, then to Glacier classes without an additional 30-day waiting period
> 	- Can be bypassed with a second rule

- Each higher tier can transition downwards into the next tier of colder access, but not upwards (except S3 One Zone-IA as noted above)
- 
>[!Warning] On the Exam
> - Ideal for:
> 	- Regional restrictions
> 	- Language specific content
> 	- Load balancing across regional endpoints
> - **Gelocation returns relevant records only - they do not [[Geoproximity Routing|return the records closest to the user]]**

- Records are tagged with a location
	- Either US state, country, continent, or default
- IP check verifies the location of the user (normally the resolver server)
- Geolocation returns relevant records, not closest
- Route 53 checks for records:
	1. in the state
	2. in the country
	3. the continent
	4. (optional) default - returns the most specific record or "no answer"
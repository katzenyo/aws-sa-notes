- It's always a bad idea to run databases on EC2
	- However, some businesses *might* benefit from it? Maybe?

## Why would you do this?

- If you need access to the DB instance OS (question this statement)
	- Situations where this is a requirement are exceedingly rare
- Advanced DB Option tuning (dbroot)
	- Question whether this is actually required, make them justify it
	- Vendors often demand this
- DB or DB Version that AWS doesn't provide
- Specific OS/DB combination that AWS doesn't offer
- Decision makers 'just want it'
	- Accept the stupidity of 'decision makers'

## Why you SHOULDN'T put a DB on an EC2

- Admin overhead
	- Managing and maintining EC2 and DBHost
- Backup/disaster recovery management
- Features
	- You lose out of on amazing features of AWS' DB offerings
- EC2 is on/off
	- No serverless, no simple scaling
	- Base minimum cost for hourly rate
- Replication
	- Skills, setup time, monitoring & effectiveness must be manually configured
- Performance
	- AWS invested time into optimizing/features
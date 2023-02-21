>[!Summary] The Problem
> - [[DNS Record Types#A & AAAA Records|A record]] maps a NAME to an IP address
> 	- e.g. catagram.io to 1.3.3.7
> - [[DNS Record Types#CNAME (Canonincal Name) Records|CNAME]] maps a NAME to another NAME
> 	- e.g. www.catagram.io to catagram.io
> 	- Can't be used for naked/apex domain (e.g. catagram.io)
> - Many AWS services don't provide an IP and require a DNS name (Elastic Load Balancers)
> 	- With CNAME alone, wouldn't be supported

## ALIAS record

>[!Warning] On the Exam
> - For any AWS services, default to using an ALIAS record in a domain
> 	- API Gateway, CloudFront, Elastic Beanstalk, ELB, Global Accelerator, S3
> - Can be used both for naked/apex and normal records
> - Should be the same "Type" as what the record is pointing at
> 	- e.g. A record ALIAS, CNAME record ALIAS, TXT record ALIAS, etc
> - Only available if you're using Route 53 for hosting domains

- ALIAS records map a NAME to an AWS resource
- Can be used both for naked/apex and normal records
- For non-apex/naked, functions like a CNAME
- There is no charge for ALIAS requests pointing at AWS resources
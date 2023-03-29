## Nameserver (NS) Records

- Allows delegation to occur in DNS

## A & AAAA Records

- Maps hostnames to IP addresses
- A record: IPv4 address
- AAAA record: IPv6 address
- Both records will be created in most cases

## CNAME (Canonical Name) Records

>[!Warning] On the Exam
>CNAMEs cannot point directly at an IP address, only other hostnames

- Hostname to Hostname records

## MX (Mail Exchange) Records

- Two main parts
	- Priority: e.g. 10,20,30,etc, lower values = higher priority
	- Value: mail, mail.other.server., denote where the MX record is pointing

## TXT Records

- **Commonly used to prove domain ownership**
- Can be used to fight spam

## TTL (Time to Live)

- Numeric value, in seconds
- Indicates how long DNS records can be cached for
	- E.g. a 3600 TTL record stores records at the resolver server for 3600 seconds
	- Allows for a non-authoritative answer, much faster than walking the tree for an authoritative answer
- Low values mean more queries against nameservers and less control
- TTL values in DNS can often cause project failures
	- When changing DNS records, always lower the TTL value ahead of the work (days or even weeks in advance) to mitigate caching issues
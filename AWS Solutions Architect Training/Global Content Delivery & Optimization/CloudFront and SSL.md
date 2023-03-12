>[!Warning] On the Exam
> - SSL supported by default (`*.cloudfront.net cert`)
> - Generate or import a cert in ACM in ***us-east-1*** for CloudFront
> - CloudFront doesn't support self-signed certs for SSL - they must be public

- CloudFront receives a default domain name (CNAME)
- https://d234234dfjlkasjdf.cloudfront.net/
- SSL supported by default
- Alternatve Domain Names (CNAME) feature
- Verify ownership (optionally HTTPS) using a matching cert
- Supports HTTP or HTTPS, HTTP -> HTTPS conversion, or HTTPS Only
- Two SSL connections: Viewer -> CloudFront and CloudFront -> Origin

## CloudFront and SNI

- Historically every SSL enabled site/cert required its own IP address
- Encryption starts at the TCP connection
	- Host headers happen after this (Layer 7/Application layer)
- SNI is a TLS extension, allows a host to be included
	- Results in many SSL certs/hosts to use a shared IP
- Older browsers don't support SNI
	- CloudFront charges extra for dedicated IPs ($600 per month per IP)

## Architecture

![[Pasted image 20230311181859.png]]
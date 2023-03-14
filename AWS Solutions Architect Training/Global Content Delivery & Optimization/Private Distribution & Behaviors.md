>[!Warning] On the Exam
> - Private requests require signed cookie or URL
> - Old method - Cloudfront key is created by account root user
> 	- Account is added as a **trusted signer**
> - New method - Trusted key groups are created
> 	- Doesn't require account root user for mgmt
> - SignedURLs provide access to one object only
> - Cookies provide access to groups of objects

- Public - open access to objects
- Private - requests require signed cookie or URL
- A single behavior (entire distribution) is either public or private
	- Implementations have multiple behaviors

## Signed URLs vs Cookies

- SignedURLs provide access to one object only
- Historically RTMP distributions couldn't use cookies
- Use URLs if client doesn't support cookies
- Use cookies for groups of files/file types
- For maintaining application URLs

## Private Distributions Architecture

![[Pasted image 20230313195757.png]]
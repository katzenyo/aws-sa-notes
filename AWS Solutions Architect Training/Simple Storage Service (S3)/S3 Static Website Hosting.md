- Access normally conducted via AWS APIs
- Static website hosting allows access via HTTP(s)
- Process: enable, set index and error documents
- Website Endpoint is created
	- Endpoint name is automatically generated
- Custom domain via R53, but bucket name matters

- Offloading: data stored (offloaded) in S3
- Out-of-band: if server/EC2 is down, maintenance notices can be delivered by S3
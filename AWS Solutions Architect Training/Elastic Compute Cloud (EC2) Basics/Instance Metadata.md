>[!Warning] On the Exam
> Metadata service is not authenticated or encrypted, anyone with access to the instance command line can query the metadata

- EC2 service provides data to instances
- Accessible inside all instances
	- http://169.254.169.254
	- http://169.254.169.254/latest/meta-data - exact metadata link
		- This will be on the exam
- Environment metadata
	- Metadata allows anything running on the instance to be queried
	- Metadata information is divided into categories
		- Hostnames, events, security groups, etc
- Networking metadata
- Authentication metadata
- User-Data metadata
- Metadata service
	- Is not authenticated or encrypted
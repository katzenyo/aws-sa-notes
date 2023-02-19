>[!Important] Key points
> - Opaque to EC2
> 	- Simply a block of data
> - NOT secure
> 	- Don't use for passwords or long term creds
> - User data is limited to 16KB in size
> - User Data can be modified when instance stopped
> 	- Contents of User Data is only executed once at launch
> 		- Used for the one initial launch of the instance

- Most powerful features of EC2
- Allows EC2 Build Automation
- User Data
	- Accessed via metadata IP
	- http://169.254.169.254/latest/user-data
	- Anything in User Data is executed by the instance OS
	- Launchtime configuration ONLY
- EC2 doesn't interpret, just passes data to the OS
	- OS needs to understand the User Data

## Architecture

- AMI used to create EBS volume
	- EBS volume is attached to the EC2 instance
	- Based on block device mapping inside AMI
- EC2 service provides User Data to EC2 instance
	- Software runs inside EC2 instance for ingesting User Data
	- User Data is executed on launch of instance
- Two outcomes
	- Running, ready for service
		- User Data config was good
	- Instance runs, still passes data checks but is not configured properly
		- Bad User Data config

## Boot-Time-to-Service-Time

- How quickly a service is ready after boot
- Measured in minutes
- Post Launch Time
	- Time taken to implement services after launch
	- Can be increased via bootstrapping
- Can be increased via AMI Baking
	- Frontloading the work (doing it in advance)
	- Reduces flexibility of config because it's baked in from the start
- Optimal way
	- Combine both AMI Baking and Bootstrapping
	- Use AMI Baking for time-intensive processes
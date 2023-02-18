## Overview

- Managed Container image registry service
	- Similar to Docker hub but for AWS
- Each AWS account has a public and private registry
- Each registry can have many repos
- Each repo can contain many images
- Images can have several tags
- Public = public R/O
	- R/W requires permissions
- Private
	- Permissions required for any R/O or R/W activity

## Benefits

- Integrated with IAM for permissions
- Image scanning
	- Basic and enhanced (inspector)
- Near real-time metrics
	- CloudWatch (auth, push, pull)
- API Actions go to CloudTrail
- Events go to EventBridge
- Replication
	- Cross-region and cross-account
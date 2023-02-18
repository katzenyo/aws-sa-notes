
- AWS Managed Kubernetes
	- Open source, cloud agnostic
	- Supported on AWS, Outposts, EKS Anywhere, EKS distro
- Control Plane scales and runs on multiple AZs
- Integrates with AWS services
	- ECR, ELB, IAM, VPC
- EKS Cluster = EKS Control Plane & EKS Nodes
- etcd distributed across multiple AZs
- Nodes
	- Self managed, managed node groups, or Fargate pods
	- Windows, GPU, Inferentia, Bottlerocket, Outposts, Local Zones
	- Check node type
- Storage Providers for persistent storage
	- EBS, EFS, FSx Lustre, FSx for NetApp ONTOP

## EKS Architecture

![[Pasted image 20230218130312.png]]
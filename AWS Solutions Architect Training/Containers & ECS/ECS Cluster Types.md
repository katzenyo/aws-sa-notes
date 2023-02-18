
## EC2 Mode

- Handles scheduling, orchestration, cluster management, placement engine
- Creates an EC2 cluster running within a VPC inside the AWS account
	- Benefits from the multiple AZs inside the VPC

## Fargate Mode

- Doesn't require management of EC2 instances or container hosts
- Fargate Shared Infrastructure Platform
	- Resources from a shared pool, isolated from other customers
- Still uses cluster + VPC
- Tasks are injected into VPC via [[Network Interfaces, Instance IPs, and DNS|ENI (Elastic Network Interface)]]

## EC2 vs ECS (EC2) vs Fargate

- If already using containers, use ECS
- For large workloads and price consciousness, use EC2 Mode
- Large workloads, but overhead conscious, use Fargate mode
- Small/burst workloads, use Fargate
- Batch/periodic workloads, use Fargate
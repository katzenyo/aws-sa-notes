>[!Abstract] Overview
> - Cluster
> 	- Deployment of Kubernetes, management, orchestration, etc
> - Node
> 	- Resources
> 	- Pods are placed on nodes to run
> - Pod
> 	- One or more ceontainers
> 	- Smallest unit in Kubernetes
> 	- Often 1 container-1 pod setup
> - Service
> 	- Abstraction
> 	- Service running on 1 or more pods
> - Job
> 	- Ad-hoc
> 	- Creates one or more pods until completion
> - Ingress
> 	- Exposes a way into a service
> 	- Ingress > Routing > Service > One or more pods
> - Ingress Controller
> 	- Used to provide ingress
> 	- e.g. AWS LB (load balancer) controller uses ALB/NLB
> - Persistent Storage (Persistent Volume)
> 	- Volume whose lifecycle persists any 1 pod using it

## Cluster Structure

- Highly available cluster of compute resources
	- Organized to work as one unit
- **Cluster Control Plane**
	- Manages the cluster, scheduling, applications, scaling, and deploying
- **Cluster Nodes**
	- VM or physical server which functions as a worker in the cluster
	- **Containerd** or Docker software for handling container operations, container runtime
	- **kubelet**
		- Agent to interact with the cluster control plane
- **Kubernetes API**
	- Used for communication between control plane and kubelet agent

### Cluster Detail Structure

- Pods
	- Smallest unit of computing in Kubernetes
	- Shared storage and networking
	- one container-one pod architecture is common
	- Pods are nonpermanent/ephemeral
	- Not highly available
- kube-apiserver
	- Frontend for Kubernetes control plane
	- Nodes and other cluster elements interact with this
	- Can be horizontally scaled for HA and performance
- etcd
	- Highly available key value store used within the cluster
	- Used as main backing store for the cluster
- kube-scheduler
	- Identifies any pods without an assigned node and assigns a node based on resource requirements, deadlines, affinity/anti-affinity, data locality, and any constraints
- cloud-controller-manager (optional)
	- Cloud-specific control logic
	- Allows linking between Kubernetes and cloud provider APIs (AWS, Azure, GCP)
- kube-controller-manager (collection of processes)
	- Node Controller
		- monitors and responds to node outages
	- Job Controller
		- One-off tasks (jobs)
	- Endpoint Controller
		- Populations endpoints
	- Service Account & Token Controllers
		- Accounts/API tokens
- kube-proxy
	- Network proxy, coordinates network within the control plane
	- Runs on each node in a cluster
	- Helps implement services and configure rules allowing network comms  with pods from both inside and outside the cluster
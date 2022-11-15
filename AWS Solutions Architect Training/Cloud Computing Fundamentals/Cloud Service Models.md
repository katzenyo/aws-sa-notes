- Infrastructure stack
	- Application
	- Data
	- Runtime environment
	- Container (docker, kubernetes)
	- O/S (Windows, Linux)
	- Virtualization
	- Servers
	- Infrastructure
	- Facilities
- Unit of consumption: the part in the stack and above that you're responsible for
	- E.g. if you have a virtual server, the unit of consumption is the virtual machine
	- Since a virtual machine is just an operating system and resources, the unit of consumption is the operating system

With on-prem, the organization must own, maintain, and be responsible for every layer of the infrastructure stack

![[Pasted image 20221114155623.png|200]]

## Infrastructure as a Service (IaaS)
- Provider manages the facilities, storage, networking, servers, and virtualization
	- Unit of consumption is the operating system
- Substantial cost reduction
- AWS EC2 is an IaaS model

![[Pasted image 20221114160439.png|200]]

## Platform as a Service (PaaS)
- Unit of consumption is runtime environment
- Provider manages rest of the stack
- Mainly used for development

![[Pasted image 20221114160611.png|200]]

## Software as a Service (SaaS)
- Consume application and nothing else

![[Pasted image 20221114160857.png|200]] 
>[!Abstract] Key Concepts
> - Dockerfiles are used to build images
> - Portable: self-contained, always run as expected
> - Lightweight: parent OS used, file system layers are shared
> - Container only runs the app & environment it needs
> - Provides similar levels of isolation as VM's
> - Ports are exposed to the host and beyond
> - App stacks can be multi-container

## Virtualization Problems

- Virtualization: OS virtualization
	- Running multiple OS on the same hardware
	- Guest OS can take up 70% of the disk with each unique image/install
	- Guest OS install adds significant storage, compute, overhead
		- Containerization solves these problems

## Containerization

- Container engine runs on top of host OS
- Container engine runs an isolated container of apps/services that behave like an isolated OS

## Image Anatomy

- Containers are Docker images
	- Docker file is used to create a Docker image
		- Each step creates fs (file system) layers
	- Created either from scratch or using a base image
	- Changes made to the Docker image are layered on top of each other
		- OS layer is read-only, app layer is read-only and on top of the OS, etc

## Container Anatomy

- Docker Container is simply a running copy of a Docker image, but with an additional R/W file system layer
	- Anything that happens in the layer (app generates or reads data, log files generated, etc) is stored in the R/W file system layer

## Container Registry

- Repository of container images (e.g. Docker Hub)
- Docker File is used to create Container Image
	- Image is then uploaded to private or public repository
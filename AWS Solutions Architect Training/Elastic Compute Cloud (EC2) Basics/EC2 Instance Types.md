- Raw CPU, memory, local storage capacity & type
- Resource Ratios
	- Keep in mind costs
- Storage & data network bandwidth
	- Instance can be limiting factor
- System architecture/vendor
	- Intel, AMD, etc
- Features & capabilities
	- GPU, FPGAs, etc

## EC2 Categories

- General Purpose
	- Default
	- Diverse workloads, equal resource ratio
- Compute Optimized
	- Media processing, HPC, Scientific modeling, gaming, machine learning
- Memory optimized
	- Processing large in-memory datasets, database workloads
- Accelerated Computing
	- Hardware GPU, field programmable gate arrays (FPGAs)
- Storage Optimized
	- Sequential and Random IO
	- Scale out transactional databases
	- Data warehousing
	- Elasticsearch
	- Analytics workloads

## Decoding EC2 Types

- Naming Schema
	- `R5dn.8xlarge` - Instance Type
		- `R` - Instance Family
		- `5` - Generation
		- `dn` - Additional Capabilities
			- `a` - AMD CPU
			- `C` - Compute
			- `d` - NVMe storage
			- `D` - Dense storage
			- `G` - GPU
			- `I` - Input/Output (IO)
			- `n` - Network optimized
			- `P` - Parallel processing
			- `e` - Extra capacity
			- `R` - RAM
		- `8xlarge` - Instance Size

Categories | Type | Details
--- | --- | ---
General Purpose | A1, M6g | Graviton (A1), Graviton 2 (M6g) ARM-based processors. Efficient.
General Purpose | T3, T3a | Burst Pool - Cheaper with nominal levels of usage and occasional peaks
General Purpose | M5, M5a, M5n | Steady state workload alternative to T3/3a - Intel/AMD
Compute Optimized | C5, C5n | Media encoding, scientific modeling, gaming, machine learning
Memory Optimized | R5, R5a | Real time analytics, in-memory caches, some DB apps (in-memory)
Memory Optimized | X1, X1e | Large scale in-mem apps, lowest $/GB memory in AWS
Memory Optimized | High Mem (u-Xtb1) | Highest memory in AWS
Memory Optimized | z1d | Large memory and CPU - directly attached NVMe
Accelerated Compute | P3 | GPU (Tesla v100) - parallel processing & machine learning
Accelerated Compute | G4 | GPU (NVIDIA T4 Tensor) - machine learning, graphics intensive
Accelerated Compute | F1 | Field Programmable Gate Arrays (FPGA) - Genomics, financial analysis, Big Data
Accelerated Compute | Inf1 | Machine learning - recommendation, forecasting, analysis, voice, conversation
Storage Optimized | I3/I3en | NVMe - NoSQL db's, warehousing, analytics
Storage Optimized | D2 | HDD - data warehouse, HADOOP, distributed file systems, data processing, lowest price throughput
Storage Optimized | H1 | High throughput, balance CPU/mem. HDFS, MAPR-FS, file systems, Apache Kafka, Big data


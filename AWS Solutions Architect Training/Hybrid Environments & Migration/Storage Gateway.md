
## Overview

>[!Warning] On the Exam
> - Ideal for migrations, extensions, storage tiering, disaster recovery, and replacement of backup systems
> - If the exam mentions
> 	- 'volumes', default to Volume Gateway
> 	- 'tape', default to [[Storage Gateway#Tape (VTL) Mode|VTL mode]]
> 	- 'files', default to [[Storage Gateway#File Mode|File mode]]
> 	- 'NFS or SMB' default to File mode

- Virtual machine (or hardware appliance)
- Presents storage using iSCSI, NFS, or SMB
- Integrates with EBS, S3, and Glacier within AWS

## Volume Stored

>[!Warning] On the Exam
> - iSCSI
> - Raw block devices
> - Everything is stored locally, on prem
> - Ideal for:
> 	- Full disk backups of servers
> 	- Helps with DR (create EBS volumes in AWS)
> 	- Doesn't extend datacenter capacity
> 		- Main copy of data is stored on the gateway
> - If you see "volume" mode mentioned on the exam, it means Volume Stored

### Architecture

![[Pasted image 20230316111627.png]]

## Volume Cached

>[!Warning] On the Exam
> - Primary data is stored on S3 (AWS)
> 	- Compare to volume stored, where data is stored locally on prem
> - Frequently accessed data is stored locally (cached)
> - Ideal for capacity extension

### Architecture

![[Pasted image 20230316113142.png]]

## Tape (VTL) Mode

>[!Warning] On the Exam
> - For any answers about tape, VTL mode is usually the correct answer

- Large backups to tape
- LTO (linear tape open)
	- Can hold 24TB of raw data
	- 60TB compressed
- 1 tape drive can use 1 tape at a time
	- Sequential storage
- Tape loader
	- Swaps tapes automatically
- Library is 1+ drives, 1+ loaders, and slots
- Drive, library, and shelf (stored anywhere that isn't the library)

### Architecture

![[Pasted image 20230316114826.png]]

## File Mode

>[!Warning] On the Exam
> - Bridges on prem file storage and AWS S3
> - Creates mount points (shares)
> 	- NFS for Linux
> 	- SMB for Windows
> - Files stored on a mount point are visible as objects in an S3 bucket
> 	- S3 objects are visible as on prem files
> - Primary data is stored in S3

- Map directly onto an S3 bucket
- Read and write caching to ensure fast, LAN-like performance
- Doesn't support object locking
	- use read only mode on other shares or tightly control file access
- Use the `notifywhenuploaded` API to notify other gateways on object change

### Architecture

#### Multiple Contributors and Replication

![[Pasted image 20230316125433.png]]

#### With S3 Lifecycle

![[Pasted image 20230316132856.png]]
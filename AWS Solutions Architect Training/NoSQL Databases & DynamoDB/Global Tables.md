>[!Warning] On the Exam
> - Replication is generally sub-second
> - Ideal for global high availability, or global disaster recovery/business continuity
> - Last writer wins conflict resolution

- Multi-master cross-region replication
- Tables are created in multiple regions
	- Then they're added to the same global table (becoming replica tables)
- Last writer wins used for conflict resolution
- Reads/writes can occur in any region
- Sub-second replication between regions
- Strongly consistent reads only in the same region as writes
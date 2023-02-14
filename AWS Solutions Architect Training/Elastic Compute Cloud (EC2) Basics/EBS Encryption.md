>[!Warning] On the Exam
> - AWS Accounts can be set to encrypt by default
> 	- Can use default KMS key
> 	- Or manually choose a KMS key to use
> 	- Key is not used to encrypt/decrypt volumes, it's used to generate a **per-volume unique DEK**
> - **Snapshots & future volumes from the same snapshot use the exact same DEK**
> - Can't change a volume to be unencrypted once encrypted
> - OS isn't aware of encryption
> 	- Encryption occurs between EC2 host and volume, EC2 instance isn't involved
> 	- Results in no performance loss on the EC2 instance
> - Software disc encryption (encryption that occurs on the EC2 instance/OS) if absolutely necessary
> - Doesn't cost anything to use, very efficient

## Basic Architecture

![[Pasted image 20230212171529.png]]


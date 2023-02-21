>[!Warning] On the Exam
> - KMS creates an asymmetric key pair (public and private keys)
> 	- Hosted in `us-east-1`
> - Creation and management/rotation of Zone Signing Keys is handled internally by Route 53
> 	- KMS is not involved, it only creates the initial asymmetric key pair required to generate the ZSK
> - Create CloudWatch Alarms
> 	- `DNSSECInternalFailure`
> 	- `DNSSECKeySigningKeysNeedingAction`
> 	- Both alarms indicate problems that require immediate action and are important for mainting security
> - Enable DNSSEC Validation for VPCs
> 	- Invalid results on DNSSEC enabled zones won't be returned
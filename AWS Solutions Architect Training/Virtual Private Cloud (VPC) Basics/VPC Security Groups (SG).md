- Stateful: detect response traffic automatically
- Allowed (in or out) request = allowed response
- No explicit deny: only allow or implicit deny
	- **Can't be used to block certain IPs**
- Supports IP/CIDR
	- Logical resources including other security groups and itself
- Attached to network interfaces
	- Not attached to instances (even if it appears that way)

## Logical References

- A VPC security group on one subnet can reference a different subnet to allow traffic through from that subnet

>[!Warning] On the Exam
> - Logical referencing scales
> 	- Any new instances which use a security group from one subnet that is referenced by a second subnet, are allowed to communicate with any instances using the second subnet (the subnet doing the referencing)

### Self References

>[!Warning] On the Exam
> - IP changes handled automatically
> - Intra-app communication (MS Domain Controllers, App HA)

- An security group source means "anything with the security group attached"
- Self reference means "anything with this security group attached"
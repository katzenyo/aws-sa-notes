>[!Definition] The Basics
>- Logical containers (groupings) for IAM Users
>- IAM Users can be members of multiple groups
>- Can have policies (inline, managed) attached
>- Can hold identity permissions
>- There is no native "All Users" group
>	- Any group containing all users would need to be custom created and self-managed
>- No group nesting allowed
>- Limit of 300 groups per account
>	- Can be increased manually by AWS support
>- Can't be referenced as a principal in a policy
>	- A resource policy can't grant access to an IAM group
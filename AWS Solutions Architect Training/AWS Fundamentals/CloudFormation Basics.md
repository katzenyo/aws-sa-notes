>[!Abstract] The Basics
> - Resources section of a template is the only mandatory part of a CloudFormation template

Sample CloudFormation Template:

>[!Warning] On the Exam
>If the `AWSTemplateFormatVersion` parameter is present in the CloudFormation template, the `Description` parameter **must** immediately follow the format version parameter.

```yml
AWSTemplateFormatVersion: "version date"

Description:
	String (if AWSTemplateFormatVersion is present this parameter must immediately follow like so)

Metadata:
	template metadata (controls the UI appearance)

Parameters:
	set of parameters (user prompt fields)

Mappings:
	set of mappings

Conditions:
	set of conditions (conditional behavior)

Transform:
	set of transforms

Resources:
	set of resources

Outputs:
	set of outputs
```

- Resources defined inside templates are called *logical resources*
	- Logical resources have types and properties
- Stack: an active implementation of a template
	- A single template can create multiple stacks
	- For all logical resources in the stack, CloudFormation creates a corresponding physical resource in the specified AWS account
	- Stacks can be updated by updating its corresponding template
	- If a stack is deleted, the corresponding physical resources are also deleted
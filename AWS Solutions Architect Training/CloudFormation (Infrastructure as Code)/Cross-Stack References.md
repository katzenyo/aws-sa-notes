>[!Warning] On the Exam
> - Stacks are designed to be isolated and self-contained
> - Outputs can be exported, making them visible to other stacks
> 	- Exports must have a unique name per region
> 	- `Fn::ImportValue` is used instead of Ref
> - Ideal for:
> 	- Service-oriented architectures
> 	- Stacks with varying lifecycles
> 	- Reusing resources in a stack

- Outputs are normally not visible to other stacks
	- But nested stacks can reference outputs

## Architecture

![[Pasted image 20230319173408.png]]
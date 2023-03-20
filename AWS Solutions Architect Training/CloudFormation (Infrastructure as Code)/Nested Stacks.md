>[!Warning] On the Exam
> - Resources in a single stack share a lifecycle
> - Whole templates can be reused in other stacks
> - Use nested stacks when stacks form part of one solution (lifecycle linked)

- Stacks are limited to 500 resources per stack
- Can't easily reuse resources defined in a stack, such as a VPC
- Can't easily reference other stacks

## Structure

![[Pasted image 20230319171106.png]]

## Main Benefits

- Overcome 500 resource limit of a single stack
- Allows for modular templates (code reuse)
- Makes installation process easier
- **Use only when everything is lifecycle linked**
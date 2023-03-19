
- Ref & `Fn::GetAtt`
- `Fn::Join` & `Fn::Split`
- `Fn::GetAZs` & `Fn::Select`
- Conditions
	- `Fn:: IF, And, Equals, Not & Or`
- `Fn::Base64` & `Fn::Sub`
- `Fn::Cidr`

## Ref and `Fn::GetAtt`

- !Ref Instance
	- !Ref on a template or pseudo parameter returns their value
	- When used with logical resources, the physical ID is returned
- !GetAtt LogicalResource.Attribute
	- Can be used to retrieve any attribute associated with the resource
	- Most logical resources return detailed configuration of the physical resource

## `Fn::GetAZs` and `Fn::Select`

- !GetAZs
	- Returns a list of AZs in the explicit region, or current region
- Fn::Select or !Select
	- Returns an object from a list of objects
	- Lists atart at index 0 (the first object)

![[Pasted image 20230319123816.png]]

## Fn::Join and Fn::Split

![[Pasted image 20230319124052.png]]

## Fn::Base64 and Fn::Sub

![[Pasted image 20230319124605.png]]

## Fn::Cidr

![[Pasted image 20230319124731.png]]
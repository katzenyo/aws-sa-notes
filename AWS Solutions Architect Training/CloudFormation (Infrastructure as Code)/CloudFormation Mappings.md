>[!Warning] On the Exam
> - Mappings are used to improve template portability

- Templates can contain *Mappings* to an object
	- They can contain many mappings, which can map keys to values and allow lookup
- Can have one key, or Top & Second Level keys
- Mappings use the !FindInMap intrinsic function
- Commonly used to retrieve an AMI for a given region & architecture
- Format:
	- `!FindInMap [ MapName, TopLevelKey, SecondLevelKey ]`
	- e.g. `!FindInMap [ "RegionMap", !Ref 'AWS::Region', "HVM64"`

![[Pasted image 20230319125105.png]]
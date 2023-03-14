
- Allows running of lightweight Lambda functions at edge locations
- Adjusts data between the viewer & origin
- Currently supports only Node.js and Python
- Runs in the [[AWS Public vs Private Services#AWS Public Zone|AWS Public Zone]]
- Layers are not supported
- Different Limits vs Normal Lambda Functions

## Architecture

![[Pasted image 20230314011018.png]]

## Use Cases

- Viewer Request
	- A/B Testing
- Origin Request
	- Migration between S3 Origins
	- Different objects based on device
	- Display content by country
- Workflows
	- Used to import data that can be executed by [[AWS Glue]] crawlers
	- Defines data source and schedule to import data into data lake
	- Can be defined using blueprints or templates
	- Must be granted IAM role that grants Lake Formation permission to ingest data
- Data Lake Administrator
	- The only IAM user/role that can initially grant permissions on data locations and Data Catalog resources to any principal (including itself)
	- `lakeformation:PutDataLakeSettings`
	- `lakeformation:GetDataLakeSettings`
	- Should not have `AdministratorAccess`

## Architecture

![[Pasted image 20230401023019.png]]
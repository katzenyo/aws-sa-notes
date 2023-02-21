
## Relational (SQL) vs Non-Relational (NoSQL)

- Structured Query Language (SQL)
- Structure in and between tables of data
	- Relational databases: Rigid Schema
	- Difficult to change data
	- Difficult to store data where relationships are changing often
	- Relationships between tables
- NoSQL: Not one single model of database
	- Weak Schemas or No Schemas
	- Relationships handled differently

## Relational Databases

- Data that relates together is stored in a table
- Primary Key
	- Every row must have a unique value
- Composite Key
	- Key formed from two parts
	- Used to join tables/form relationships

## NoSQL Databases

### Key-Value Databases

>[!Warning] On the Exam
> - Questions with 'simple requirements' or mention data that are just 'names and values', 'pairs', or 'keys and values' are referring to key-value databases
> - Make note of questions that refer to in-memory caching
> 	- These are also referring to key-value databases

- List of keys with corresponding values
- No Schema & no structure
- Very scalable
- Adjust data very quickly

### Wide Column Store

- Two keys
	- Partition Key
	- Other (additional) keys
- Groupings of data called tables (but not a SQL table)
- Attributes
	- Any item can have none, one, or multiple attributes
- Every item in the table must:
	- use the same key structure
	- have a unique key
- DynamoDB
	- Wide Column Store
	- Fast, scalable
	- Used in web scale or large scale projects

### Document Database

- Store and query data as documents
- Formatted using JSON or XML
	- Format can vary throughout the database
- Flexible indexing
- Ideal for:
	- Orders
	- Contacts
	- Interacting with whole documents
	- Deep attribute interactions

### Column Databases

- Row Store (MySQL)
	- Every item is stored as a row
	- Ideal for working with rows - adding, updating, deleting
	- Online Transaction Processing (OLTP)
- Column Store (Redshift)
	- Columns of data stored together
	- Inefficient for transaction processing
	- Ideal for:
		- Reporting and Analytics
		- When all values for a specific attribute (size) are required

### Graph Databases

- Ideal for:
	- Social media, HR software
	- Systems with complex relationships
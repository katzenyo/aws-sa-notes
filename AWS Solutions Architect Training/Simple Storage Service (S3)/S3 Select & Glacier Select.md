>[!Warning] Exam PowerUp
> - Often want to retrieve an entire object
> - Larger objects take more time to retrieve
> - Client-side filtering doesn't reduce the time
> - SQL-like statements allow you to select parts of an object, pre-filtered by S3

- Allow you to use SQL-like statements
- Works on various formats including CSV, JSON, Parquet, BZIP2


## Without S3 Select Filtering

- When apps retrieve objects from S3, the entire object is delivered
- Filtering occurs on the app side and is simply discarded after already being delivered

## With S3 Select Filtering

- Filtering is done from the S3 side using SQL-like expressions
- Allows for only parts of 
- 400% faster, 80% cheaper
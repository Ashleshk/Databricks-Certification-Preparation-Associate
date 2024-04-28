# Udemy Practice Exam 2

- SQL commands are used to append rows to an existing delta table:
- Learn about OPTIMIZE
- CREATE DATABASE command —
- DROP DATABASE
- constraints that can be enforced on Delta lake tables are supported?
- DEEP CLONE vs SHADOW CLONE
- Spark’s structured stream supports the below write mode
- cloudFiles.SchemLocation, checkpointLocation
- A DELTA LIVE TABLE pipelines can be scheduled to run in two different modes, what are these two different modes?
- How do you upgrade an existing workspace managed table to a unity catalog table?

- Use databricks cluster pool feature to reduce the startup time
- CI/CD in databricks

![Untitled](Images/exam/Untitled%202.png)

- Databricks repo - allows you to add comment and select changes you want to commit instead of databrucks allow you for merge and conflict resoliution
- DROP database and all associated tables and views
    - DROP DATABASE db CASCADE
- Read from a SQLLITE DB

```sql
CREATE TABLE users_jdbc
USING org.apache.spark.sql.jdbc
OPTIONS
	(
		url='jdbc:sqlite:/sample_db',
		dbtable='users'
	)

-- Template
CREATE TABLE <jdbcTable>
USING org.apache.spark.sql.jdbc or JDBC
OPTIONS (
    url = "jdbc:<databaseServerType>://<jdbcHostname>:<jdbcPort>",
    dbtable " = <jdbcDatabase>.atable",
    user = "<jdbcUsername>",
    password = "<jdbcPassword>"
)

```

- REFRESH TABLE to remove cache from external table
- DELTA LAKE only enforces two types of constraints - not null, check constraints
- Quickly copy: shallow clone
- Spark’s structured stream supports the below write modes: Append, Complete, Update
- When using the complete mode to write stream data, how does it impact the target table? — Target table is overwritten
- cloudFiles.schemaLocation, checkPointLocation
- In autoloader you can provide schema hints to give data types for columns

```sql
spark.readStream \
  .format("cloudFiles") \
  .option("cloudFiles.format", "csv") \
  .option("header", "true") \
  .option("cloudFiles.schemaLocation", schema_location) \
  **.option("cloudFiles.schemaHints", "id int, description string")**
  .load(raw_data_location)
  .writeStream \
  .option("checkpointLocation", checkpoint_location) \
  .start(target_delta_table_location)
```

- Delta Live table pipeline can be triggered in two modes
    - TRIGERRED, CONTINUOUS
- More than one visualization can be developed using a single query result.

![Untitled](Images/exam/Untitled%201.png)

- How do you upgrade an existing workspace managed table to a unity catalog table?
    - we are moving the data from an internal hive metastore to a metastore and catalog that is registered in the Unity catalog. note: if it is a managed table the data is copied to a different storage account, for a large tables this can take a lot of time.  For an external table the process is different.
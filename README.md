# MSSQL

<pre><code>

SELECT 
	OBJECT_SCHEMA_NAME(tables.object_id, db_id()) AS SchemaName,
	tables.name As TableName,
	identity_columns.name as ColumnName,
	identity_columns.seed_value,
	identity_columns.increment_value,
	identity_columns.last_value
FROM sys.tables tables 
	JOIN sys.identity_columns identity_columns 
ON tables.object_id=identity_columns.object_id
GO

</code></pre>

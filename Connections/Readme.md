[Index](https://github.com/KiraDiShira/Ado/blob/master/README.md#adonet)

# Establishing Connections with the Database

The **connection string** contains the information that the connection object has provided required to establish a physical connection to the database.

A connection string consists of a series of keyword value pairs separated by semicolons. 

The basic information which is required to generate the connection string are `Data Source=ServerName`, `Initial Catalog=DataBaseName`, `User id=UserName`, `Password=Secret`. 

ConnectionString to interact with the SQL Server database is 

`Provider=SQLOLEDB; Data Source=ServerName; Initial Catalog=DataBaseName; User Id=username; password=secret`

ConnectionString to interact with the Oracle Database

`Provider=oraoledb.oracle; user id=username; password=secret; data source=server`

Whenever we use SQL connection class to interact with the SQL Server database, an Oracle connection class to interact with the Oracle database, then `Provider= provider name` **is not required** within the connection string.

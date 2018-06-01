[Index](https://github.com/KiraDiShira/Ado/blob/master/README.md#adonet)

# Introducing Ado.Net

ADO.NET is framework for interacting with any database or XML documents from any .NET application.

ADO.NET supports two types of models for interacting with the database:
- disconnected model
- connection-oriented model

## ADO.NET Disconnected Model

<img src="https://github.com/KiraDiShira/Ado/blob/master/AdoDisconnected/Images/adodisco1.PNG" />

### Connection

A connection sets a link between a data source and ADO.NET. Connection object establishes the physical connectivity between the application and the database with the support of connection string.

### DataAdapter

DataAdapter is a collection of command objects, which acts like a bridge between the database and the DataSet for transferring the data.

<img src="https://github.com/KiraDiShira/Ado/blob/master/AdoDisconnected/Images/adodisco2.PNG" />

### Dataset

The DataSet object is central to supporting disconnected distributed data scenarios with ADO.NET. 

DataSet can be considered as an in-memory representation of the data at the client system. 

DataSet can interact with any number of tables present in different databases, such as SQL Server, Oracle, or XML documents. It also supports establishing the data relationship between the data tables. If any manipulations are performed on the data table of DataSet, the changes will not be reflected at the tables of the database. 

Our DataSet object can also be considered as a collection of **DataTables**, **DataRelations**, and **XMLSchema**, where our **DataTable or a DataMember** of a DataSet is a collection of **DataColumns**, **DataRows**, and **Constraints**. Whenever our DataSet object is defined with the support of XML Schema definition, then we call it a **typed DataSet**, 

<img src="https://github.com/KiraDiShira/Ado/blob/master/AdoDisconnected/Images/adodisco3.PNG" />

and without XML Schema definition, it is set to be **untyped DataSet**. 

### Dataview

DataView represents our databindable, customized view of a DataTable. The DataView does not store data, but instead represents a connected view of its corresponding DataTable. Changes to the DataView's data will affect the DataTable. Changes to the DataTable's data will affect all DataView's associated with it. DataView can be used for sorting, filtering, searching, editing, and navigation on the data.

<img src="https://github.com/KiraDiShira/Ado/blob/master/AdoDisconnected/Images/adodisco4.PNG" />

## Connection Oriented Model

The connectivity between the application and the database has to be maintained until the application interacts with the database.

**Connection-oriented model** can be used whenever we constantly make trips to the database to perform CRUD operations. This creates more traffic to the database, but is normally much faster when we perform smaller transactions. 

<img src="https://github.com/KiraDiShira/Ado/blob/master/AdoDisconnected/Images/adodisco5.PNG" />

**Command** object will use `Connection` to interact with our database, and it can interact with the application for executing the commands, and if the command is to retrieve the data, then the result of `Command` object will be passed to the `DataReader` object, which will interact with the application for projecting the data. DataReader object maintains the records retrieved by the Command object, and this object is a read-only and forward-only record set. That is, the data present within the DataReader object can be modified, and once the data has been read from the DataReader, again, we can't retrieve the previous data.

### Command

Command object is used to store SQL statements that need to be executed against a data source. 

The Command object can execute select statements, Insert, Update, Delete statements, StoredProcedure, or any valid SQL statement understood by the database. Command object has the following important properties. 

**Connection**, used to specify the connection to be used by the Command object. 

**CommandType**, used to specify the type of SQL command you wanted to execute. To assign a value to this property, we use the enumeration CommandType that has the members Text, StoredProcedures, and TableDirect. Text is the default and is set when you want to execute any SQL command with Command object. StoredProcedure is set when you want to call a StoredProcedure function. And TableDirect is set when you want to retrieve data from the table directly by specifying the table name without writing a Select statement. 

**CommandText**, used to specify the SQL statement you want to execute. 

**Transaction**, used to associate a transaction object to the Command object so that the changes made to the database with Command object can be commited or rolled back. 

Command object has the following important methods. 

**ExecuteNonQuery**, used to execute any valid SQL statement other than the Select statement. Output type of this method is int and it returns the number of rows affected by the given statement. 

**ExecuteScalar**, used to execute a Select statement that returns a single value. If the Select statement executed by the ExecuteScalar method returns more than one value, then the method returns the value present at the first row, first column retrieved by the query. ExecuteScalar methods return an object. 

**ExecuteReader**, it is used to execute any valid Select statement. Return type of this method is DataReader.

### Data Reader

DataReader object in ADO.NET is a string-based read-only and forward-only record set, which maintains the records retrieved by the Command object.

This object can be used only for reading the data in forward only directions; that is, once a record has been read, again, we can go back to the previous record. 

DataReader object can be used for performing any kind of manipulations on the data. We can't define the DataReader object directly. It can be defined with the support of ExecuteReader method of command object. Whenever we use the DataReader object, it is mandatory to open the connection. While using the DataReader for accessing the data, it can be used for any other operations. 

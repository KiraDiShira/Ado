# Ado

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

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

Now let us try to understand the usage of DataAdapter. Say that we have an application and it has to interact with the database. Then, an application can interact with the database directly. If we can recollect the architecture, our application interacts with the DataSet. But the problem is, our DataSet can't interact with the database. Since the application and the DataSet can't interact with the database directly, we require a bridge such that the data from database can be passed to the DataSet, and the information present at the DataSet can be updated at the database, so our data adapter acts like a bridge for transferring the data between the DataSet and database. If we recollect, we discuss that the data adapter as a collection of command objects. The commands present within the data adapter are SELECTCOMMAND, TABLEMAPPINGS, INSERTCOMMAND, UPDATECOMMAND, and DELETECOMMAND. These commands help in transferring the data from the database to the DataSet and vice versa. Whenever we read the data from the database and provide that result to the DataSet, it is set to be fill. And if we read the data from the DataSet and update the database, then it is set to be update.

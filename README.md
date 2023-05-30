# MyAdoHelper

MyAdoHelper, but better

## Connection Class

Represents a SQL connection and provides methods for executing queries and statements.

### Properties

- `Conn`: Gets the `SqlConnection` object associated with this `Connection` instance. It is used for establishing a connection to the SQL database.

### Constructors

- `Connection(string connStr)`: Initializes a new instance of the `Connection` class with the provided connection string.
- `Connection(SqlConnection conn)`: Initializes a new instance of the `Connection` class with the provided `SqlConnection` object.

### Methods

- `DoQuery(string sql) -> int`: Executes a query SQL statement on the SQL Manager using the provided or default connection string. Returns the number of rows affected by the SQL statement.
- `ExecuteQuery(string sql) -> object[,]`: Executes a SQL query on the SQL Manager and returns the result as a two-dimensional object array.
- `DoesExist(string sql) -> bool`: Checks if a record exists in the SQL Manager based on the provided SQL query.
- `ExecuteDataTable(string sql) -> DataTable`: Executes a SQL statement and returns the result as a `DataTable` object.
- `DoNonQuery(string sql) -> int`: Executes a non-query SQL statement and returns the number of rows affected.

## Syntax Class

Represents a class that provides SQL syntax generation for MSSQL commands.

### Methods

- `Select(string tableName, string[] columns, string condition = null) -> string`: Generates a SELECT query to retrieve specified columns from a table.
- `Insert(string tableName, string[] columns, object[] values) -> string`: Generates an INSERT query to insert values into a table.
- `Update(string tableName, string[] columns, object[] values, string condition) -> string`: Generates an UPDATE query to update values in a table.
- `Delete(string tableName, string condition) -> string`: Generates a DELETE query to delete rows from a table based on a condition.
- `FormatValue(object value) -> string`: Formats a value based on its type to be used in SQL queries.

## Manager Class

Represents a class for interacting with a SQL Server SQL Manager.

### Methods

- `GetConnection(string connStr = defaultConnStr) -> SqlConnection`: Gets a new instance of `SqlConnection` using the provided or default connection string.
- `DoQuery(string sql, string connStr = defaultConnStr) -> int`: Executes a query SQL statement on the SQL Manager using the provided or default connection string.
- `ExecuteQuery(string sql, string connStr = defaultConnStr) -> object[,]`: Executes a SQL query on the SQL Manager and returns the result as a two-dimensional object array.
- `DoesExist(string sql, string connStr = defaultConnStr) -> bool`: Checks if a record exists in the SQL Manager based on the provided SQL query.
- `ExecuteDataTable(string sql, string connStr = defaultConnStr) -> DataTable`: Executes a SQL statement and returns the result as a `DataTable` object.

Note: `defaultConnStr` is a private constant that holds the default connection string for the SQL Manager.
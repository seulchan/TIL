# ALTER TABLE statement and its uses

## Commands to use with the ALTER Statement

### ADD

To add a column to an existing table, you can use the ADD command followed by the column name and data type. The syntax is as follows: 

```sql
ALTER TABLE table_name ADD column_name datatype;
```

Example:

```sql
ALTER TABLE Employees ADD Email VARCHAR(255);
```

&nbsp;

### MODIFY

To modify a column, you can use the MODIFY command followed by the column that you want to modify.

Syntax:

```sql
ALTER TABLE table_name MODIFY COLUMN column_name datatype;
```

Example: 

```sql
ALTER TABLE Employees MODIFY COLUMN Email VARCHAR(50);
```

&nbsp;

### Adding a FOREIGN KEY to an existing table using ADD

To create a link between one table and another table, you can use the FOREIGN KEY and REFERENCES commands along with the ADD command.

Syntax:

```sql
ALTER TABLE table_name ADD FOREIGN KEY (primary_key_column_name) REFERENCES link_table_name(reference_column_name);
```

Example:

```sql
ALTER TABLE Orders ADD FOREIGN KEY (CustomerID) REFERENCES Customer(CustomerID);
```

&nbsp;

### DROP COLUMN

To remove/delete an existing column from a table, you can use the DROP COLUMN command followed by the column that you want to modify.

Syntax:

```sql
ALTER TABLE table_name DROP COLUMN column_name;
```

Example:

```sql
ALTER TABLE Employees DROP COLUMN Email;
```

&nbsp;

### CHANGE

You can use the CHANGE command with the ALTER statement to rename a column.

Syntax:

```sql
ALTER TABLE table_name CHANGE from_column to_column datatype;
```

Example:

```sql
ALTER TABLE Employees CHANGE Email BusinessEmail VARCHAR(50);
```

&nbsp;

### RENAME  

The RENAME command can be used to change a table name, followed by the new name that needs to be given to the table.

Syntax:

```sql
ALTER TABLE table_name RENAME new_table_name;
```

Example:

```sql
ALTER TABLE OrderStatus RENAME OrderDeliveryStatus;
```

&nbsp;

(source: [Database Structures and Management with MySQL](https://www.coursera.org/learn/database-structures-and-management-with-mysql/))
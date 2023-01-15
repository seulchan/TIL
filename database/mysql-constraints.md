# Types of MySQL constraints

## Key Constraints

There are different types of keys in a relational database. For example, each table must have a primary key that maintains table integrity. The primary key ensures no duplications of records in the same table. Also, it allows identifying each data record using the primary key value. Therefore, it must be unique in each row of the table, and it is not allowed to contain null values. 

For example, each citizen living in Denmark must have a unique personal number, which can be used to access different types of state services.

## Domain Constraints

Domain constraints refer to special rules defined for the values that can be stored for a certain column. To apply this, you must specify what data values are allowed and which ones should be rejected. 

For example, you can define a valid range number for users to rate a streaming service that offers a wide variety of TV shows and movies. This range could be a number between 3 and 10, in which case the user will not be able to insert a value that is more than 10 and less than 3.

## Referential Integrity Constraints 

In a relational database, tables are connected via a foreign key in one table linked to a primary key (or a unique key) in another table. 

This implies that the value of the foreign key column in the ‘referencing’ table must also exist in the referenced table. Otherwise, you will end up with a problem as the “connection” between the records of the tables will cease. 

Therefore, maintaining referential integrity requires that a foreign key value must have a matching primary key value to link the records of different related tables. 
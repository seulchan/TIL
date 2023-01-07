# Database structure

## What is database structure?

Database structure refers to how data is arranged in a database. Within a database, related data are grouped into tables, each of which consists of rows (also called tuples) and columns, like in a spreadsheet.

The structure of a database consists of a set of key components. These include:      

- Tables or entities, where the data is stored. 

- Attributes which are details about the table or entity. In other words, attributes describe the table.  

- Fields, which are columns used to capture attributes. 

- A record, which is one row of details about a table or entity. 

- And the primary key, which is a unique value for an entity. 

This image shows the basic structural elements of a database table.

&nbsp;

<img src="../images/db-structure.png" alt="db-structure" width="500" style="margin-left: auto; margin-right: auto; display: block;"/>

&nbsp;

## Table

A table contains all the fields, attributes and records for a type of entity. A database will most probably contain more than one table.

&nbsp;

## Fields

Column headings are known as fields. Each field contains a different attribute. For every table, a unit of data is entered into each field. It’s also known as a column value. Each column has a data type. \

&nbsp;

## Column value or unit of data

Each individual piece of data entered into a column is a unit of data. These units are also called data elements or column values.

&nbsp;

## Records

A record consists of a collection of data for each entity. It’s also known as a row in the table.

&nbsp;

## Data types

To keep the data consistent from one record to the next, an appropriate data type is assigned to each column. The data type of a column determines what type of data can be stored in each column.

Data types are also a way of classifying data values or column values. Different kinds of data values or column values require different amounts of memory to store them. Different operations can be performed on those column values based on their datatypes.

&nbsp;

## Logical database structure

The logical structure of a database is represented using a diagram known as the Entity Relationship Diagram (ERD). It is a visual representation of how the database will be implemented into tables during physical database design, using a Database Management System (DBMS) like MySQL or Oracle, for example. 

A part of the logical database structure is how relationships are established between entities. These relationships are established between the instances of the entities. Accordingly, there can be three ways in which entity instances can be related to each other:

- One-to-one relationships 

- One-to-many relationships 

- Many-to-many relationships 

This is also known as cardinality of relationships. The logical database structure which is represented using an ERD also depicts these relationships.

&nbsp;

## Physical database structure

In the physical database structure, where entities are implemented as tables, the relationships are established using a field known as a foreign key. A foreign key is a field in one table that refers to a common field in another table (usually the primary key). 

&nbsp;

(sourece: https://www.coursera.org/learn/introduction-to-databases)
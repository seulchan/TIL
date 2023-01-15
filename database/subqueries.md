# Subqueries

## What is a sub-query?

A sub-query is a query within another query. In other words, an inner query. In a sub-query, a SQL SELECT query is placed as a part of another query called an outer query. Think of the inner query as the child query and the outer query as the parent query.

Place a sub-query in the SELECT, FROM, or WHERE clause. You will find it used in the WHERE clause most of the time. Also, always place a subquery within a pair of parentheses. There can be sub-queries that return a single value, a single row, a single column, or multiple rows of one or more columns. When writing subqueries, it is possible to use comparison operators such as =, >, >=, <, <=, != (or <>). In addition, you can also use ALL, ANY and SOME operators followed by a comparison operator.

&nbsp;

## Types of sub-queries

### Subqueries in the FROM clause

You already know that in SQL, in the FROM clause, you specify the table name in which the data in question resides. When you use a sub-query in the FROM clause, the result returned from a sub-query is used as a temporary table. 

This table is referred to as a derived table as well.

Here’s what the syntax of a sub-query in the FROM clause looks like:

```sql
SELECT some_column, some_column FROM (Subquery) AS alias;
```

&nbsp;

### Sub-queries in INSERT statements

You already know that you can use INSERT INTO SELECT statements. That means to use SELECT statements in an INSERT statement when you want to retrieve some data and insert them into another table. 

The SELECT statement here can contain a sub-query.

Here’s what the syntax of a sub-query in an INSERT statement looks like:

```sql
INSERT INTO table1 SELECT column1,column2,column3 FROM table2 WHERE some_column some_operator(Subquery);
```

&nbsp;

### Sub-queries in UPDATE statements

An update statement can also use a subquery. In the UPDATE statement’s WHERE clause, you can use a subquery to filter out the records you want to update.

Here’s what the syntax of a subquery in an UPDATE statement looks like:

```sql
UPDATE table1 SET column1 = some_value WHERE some_column some_operator(Sub-query);
```

&nbsp;

### Sub-queries in DELETE statements

You can also use sub-queries in your DELETE statement. Once again, in the WHERE clause of the DELETE statement, you can use a subquery to filter out the records you want to delete.

Here’s what the syntax of a subquery in a DELETE statement looks like:

```sql
DELETE FROM table1 WHERE some_column some_operator(Subquery);
```

&nbsp;

(source: [Database Structures and Management with MySQL](https://www.coursera.org/learn/database-structures-and-management-with-mysql/))
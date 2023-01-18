# Functions in MySQL

## What is a function in MySQL?

A function is a code that performs an operation and returns a result. Functions are used to manipulate data in a database table.

MySQL has many built-in functions that fall under different categories. These include:

- String manipulation functions
- Date and time functions
- Numeric functions
- Comparison functions
- Control flow functions

At this stage in the lesson, you should be familiar with basic examples of each of these types of functions. So let's take a few moments to explore other examples.

&nbsp;

## Numeric functions

MySQL numeric functions can be broadly divided into mathematical and aggregate functions. You've reviewed numerous examples of many MySQL aggregate functions. You've also looked at many mathematical functions. In this reading, you'll  explore a few more mathematical functions. 

Mathematical functions allow you to perform mathematical tasks on numeric data.

Let's look at two meaningful and useful mathematical functions: CEIL and FLOOR.

The CEIL function returns the smallest integer value, which is not less than the passed value. For example, passing a value of 1.23 to the CEIL function returns a value of 2.

It returns NULL if the value passed is NULL. The syntax of the CEIL function is as follows: 

```sql
SELECT CEIL(VALUE);
```

Example: The following code returns 16 as it is the smallest integer value that is greater than or equal to 15.50. 

```sql
SELECT CEIL(15.50);
```

The FLOOR function does the opposite of CEIL. It returns the largest integer value not greater than the passed value. It returns NULL if the passed value is NULL. 

Its syntax is the same as the CEIL function. It's just a matter of replacing the CEIL function with the FLOOR function.

```sql  
SELECT FLOOR(VALUE);
```

Example: The following code returns 15 as it is the largest integer value that is less than or equal to 15.50.  

```sql
SELECT FLOOR(15.50);
```

&nbsp;

## String functions

Now let's look at some more String functions like FORMAT, LENGTH and REPLACE. 

The FORMAT function formats the number passed into a format like '#,###,###.##', rounded to the specified number of decimal places. It returns the result as a string.

Here's the syntax:

```sql
SELECT FORMAT(number_to_be_formatted, number_of_decimal_places);
```

Example: The following code returns 3,750.75  as it formats the number (3750.753, 2) as "#,###.##" and rounds it within two decimal places. 

```sql
FORMAT(3750.753, 2)
```

If the number of decimal places is 0, the result has no decimal point or fractional part. If the number to be formatted or the number of decimal places is NULL, then the function returns NULL.

&nbsp;

## Date functions

You’ve explored MySQL date functions such as CURRENT_DATE, CURRENT_TIME, DATE_FORMAT and DATEDIFF. Now let’s explore a few more essential date functions with some examples.

The ADDDATE function is used to perform arithmetic with dates. It comes in two forms.

1. ADDDATE(date, INTERVAL expr unit)
2. ADDDATE(date, days)

The first argument specifies the starting date or datetime value in the first form. The second argument is an expression that determines the interval value to be added to the starting date. 

It has three parts:

1. INTERVAL is a keyword
2. expr represents a quantity
3. and unit represents the unit for interpreting the quantity; such as HOUR, DAY, or WEEK

The syntax for the first form is as follows:

```sql
SELECT ADDDATE(date, INTERVAL expr unit);
```

In the second form, the first argument is the same and the second argument is the integer, or number of days, to be added to the given date in the first argument.

Example: the following code returns 2020-05-15 because it adds 5 days to the specified date.  

```sql
SELECT ADDDATE("2020-05-10", INTERVAL 5 DAY);
```

The syntax for the second form is as follows:

```sql
SELECT ADDDATE(date, days);
```

Example: The following code returns 2020-06-25 because it adds 5 days to the specified date.  

```sql
SELECT ADDDATE("2020-06-15", 10);    
```

The QUARTER function is also a very versatile function that returns the quarter of the year for the given date. The return value is in the range 1 to 4, or NULL if date is NULL.

The syntax is as follows:

```sql
SELECT QUARTER(date_value);
```

The DATE, MONTH, YEAR and DAY functions extract the date, month, year and 'day of the month' parts respectively, of a given date or date time expression.

Example: The following code returns a value of 3. The QUARTER() function returns the quarter of the year for the given date value.

```sql
SELECT QUARTER("2020-09-15");
```

&nbsp;

## Comparison functions

You may know of a few comparison functions of MySQL like GREATEST, LEAST and ISNULL. 

COALESCE is another comparison function that takes several arguments and returns the first non-NULL argument. In case all arguments are NULL, the COALESCE function returns NULL. You can think of this function as a NULL checking function.

The syntax for this function is as follows:

```sql
SELECT COALESCE (value1, value2);
```

This function is particularly useful when you replace a column value with a NULL value with some other value.

Example: The following code returns Coursera, because the COALESCE() function returns the first non-null value in a list.

```sql
SELECT COALESCE(NULL, 'Coursera', NULL, 'Database');
```

&nbsp;

## Control flow functions

MySQL also has a function that lets you evaluate conditions and decide how the query should be executed accordingly. You should be familiar with the CASE function in MySQL and IFNULL, another function. It accepts two arguments and returns the first argument if it is not NULL. Otherwise, the IFNULL function returns the second argument. The two arguments can be literal values or expressions.

The syntax is as follows:

```sql
SELECT IFNULL(evaluated_expression, alternative_value);
```

Example: The following code returns Coursera as the value because the evaluated expression is NULL.

```sql
SELECT IFNULL(NULL, "Coursera");
```

There’s also the NULLIF function that takes in two values or expressions. If they're equal then it returns NULL. Otherwise, it returns the first value or expression.

This is an example of the syntax:

```sql
SELECT NULLIF(expression1, expression2);
```

Example: The following NULLIF() function returns 10, as it compares the two expressions (10 and 15) and returns NULL if they are equal. Otherwise, the first expression is returned. 

```sql
SELECT NULLIF(10, 15);
```

(source: [Database Structures and Management with MySQL](https://www.coursera.org/learn/database-structures-and-management-with-mysql/))
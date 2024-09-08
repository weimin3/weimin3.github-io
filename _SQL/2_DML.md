---
title: "Data Manipulation Language(DML)"
collection: SQL
permalink: /SQL/DML
excerpt: 'Those commands are used to manipulate the data within the database,including SELECT,INSERT INTO,UPDATE,DELETE.'
date: 2024-09-08
---
# SELECT
Retrieving data from one or more tables.
**Syntax**
```sql
SELECT column1, column2, ...
    FROM table_name
    WHERE condition;
```
**Example**
Retrieve all columns from the employees table
```sql
SELECT * FROM employees
```

# INSERT INTO
Adding new rows of data to a table.
**Syntax**
```sql
INSERT INTO table_name (column1, column2, ...)
    VALUES (value1, value2, ...);
```
**Example**
Insert a new employee into the employees table
```sql
INSERT INTO employees (name, department, salary)
VALUES ('John', 'Marketing', 55000);
```

# UPDATE
Modifing existing data in a table.
**Syntax**
```sql
UPDATE table_name
    SET column1 = value1, column2 = value2, ...
    WHERE condition;
```
**Example**
Update the salary of an employee in the employees table where the name is 'John'
```sql
UPDATE employees
    SET salary = 60000
    WHERE name = 'John';
```

# DELETE
Removing rows from a table based on specified criteria.
**Syntax**
```sql
DELETE FROM table_name
    WHERE condition;
```


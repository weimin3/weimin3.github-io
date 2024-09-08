---
title: "Data Definition Language(DDL)"
collection: SQL
category: Fundation
permalink: /SQL/DDL
excerpt: 'Those commands are used on the structure of database onjects like tables,indexes and schemas,including CREATE,ALTER,DROP,TRUNCATE.'
date: 2024-09-08
---
# CREATE
## Create a database
```sql
CREATE DATABASE [IF NOT EXISTS] databasename;
```
**IF NOT EXISTS** is used to prevent an error from occurring if the database already exists. Without it, attempting to create a database with the same name would result in an error.

For instance: `CREATE DATABASE IF NOT EXISTS company_db;`

## Create a table:
```sql
CREATE TABLE table_name(
    column 1 datatype,
    column 2 datatype,
    column 3 datatype,
    ...
)
```
For instance:
```sql
CREATE TABLE employees (
    employee_id INT PRIMARY KEY,
    first_name VARCHAR(50),
    last_name VARCHAR(50),
    hire_date DATE,
    email VARCHAR(50),
    salary DECIMAL(10, 2)
);
```

## Create a sequence
A sequence is a database object that generates unique numbers, often used for generating primary key values. Automatically generate unique IDs or primary key values, especially when inserting data. Useful for scenarios that require incrementing or decrementing numbers, such as order numbers or invoice numbers.
```sql
CREATE SEQUENCE sequence_name
    START WITH start_value
    INCREMENT BY increment_value;
```
The example creates a sequence starting from 1 and incrementing by 1, typically used for generating employee_id.
```sql
CREATE SEQUENCE employee_seq
    START WITH 1
    INCREMENT BY 1;
```

## Create unique index
A unique index is similar to a regular index but requires that all values in the indexed column(s) be unique.Use in scenarios where needing to ensure that values in a column are unique, such as email addresses or usernames. It helps the database validate data uniqueness during inserts.
```sql
CREATE UNIQUE INDEX index_name
    ON table_name(column1,column2,..);
```
The following example creates a unique index on the email column, ensuring that every employee's email address is unique.
```sql
CREATE UNIQUE INDEX idx_employee_email
    ON employees(emailS);
```

## Create a view
A view is a virtual table that is based on the result of a query. It does not store actual data, but providing different views of data to different users without direct access to underlying tables. Enhance security by preventing users from accessing sensitive data directly.
```sql
CREATE VIEW view_name AS
    SELECTT column1,column2,...
    FROM table_name
    WHERE condition;
```
The following example creates a view that only returns employees with salaries greater than 50,000.
```sql
CREATE VIEW employee_salaries AS
    SELECT first_name, last_name, salary
    FROM employees
    WHERE salary > 50000;
```

## Create index
An index is a structure that is used to speed up database queries. Commonly used for search, sorting, or filtering based on specific columns. Use an index when frequent access to certain columns is required.
```sql
CREATE INDEX index_name
    ON table_name(column1,column2,..);
```
The following example creates an index on the last_name column of the employees table to speed up queries based on last_name.
```sql
CREATE INDEX idx_employee_lastname
    ON employees(last_name);
```

## Create a user
```sql
CREATE USER 'username'@'hostname' IDENTIFIED BY 'password';
```
For instance: `CREATE USER 'admin'@'localhost' IDENTIFIED BY 'password123';`

## Create a role
```sql
CREATE ROLE role_name
```
For instance: `CREATE ROLE manager`


# ALTER
The ALTER statement is used to modify **existing objects** in a database, such as tables,columns,constraints, and more.
## Rename Table
```sql
ALTER TABLE old_table_name
    RENAME TO new_table_name;
```

## Add a Column
```sql
ALTER TABLE table_name
    ADD COLUMN column_name data_type;
```

## Drop a Column
```sql
ALTER TABLE table_name
    DROP COLUMN column_name;
```

## Modify data type of a Column
```sql
ALTER TABLE table_name
    MODIFY COLUMN column_name new_data_type;
```

## Rename column
```sql
ALTER TABLE table_name
    RENAME COLUMN column_name TO new_column_name;
```

## Add Constraint
```sql
ALTER TABLE table_name
    ADD CONSTRAINT constraint_name constraint_type (column_name);
```
```sql
ALTER TABLE employees
    ADD CONSTRAINT fk_department
    FOREIGN KEY (department_id) REFERENCES departments(department_id);
```
Adds a foreign key constraint named fk_department on the department_id column referencing departments(department_id).

## Drop Constraint
```sql
ALTER TABLE table_name
    DROP CONSTRAINT constraint_name;
```
```sql
ALTER TABLE employees
    DROP CONSTRAINT fk_department;
```
Removes the foreign key constraint fk_department from the employees table.

## Change Default Value
```sql
ALTER TABLE table_name
    ALTER COLUMN column_name SET DEFAULT default_value;
```
```sql
ALTER TABLE employees
    ALTER COLUMN hire_date SET DEFAULT CURRENT_DATE;
```
Sets the default value of the hire_date column to the current date.

# DROP
## Drop database
```sql
DROP DATABASE [IF EXISTS] database_name;
```
## Drop table
It is used to remove an entire table from a database, including all its data and structure.
```sql
DROP TABLE [IF EXISTS] table_name;
```
## Drop view
```sql
DROP VIEW [IF EXISTS] view_name;
```
## Drop index
```sql
DROP INDEX [IF EXISTS] index_name ON table_name;
```
## DROP SEQUENCE
```sql
DROP SEQUENCE [IF EXISTS] sequence_name;
```
# TRUNCATE
The TRUNCATE statement is used **to remove all rows from a table** quickly and efficiently, **without removing the table itself**.
```sql
TRUNCATE TABLE table_name;
```

**Differences Between TRUNCATE and DELETE**
- DELETE: Can remove specific rows based on a WHERE clause, and can activate triggers. It logs each row deletion.
- TRUNCATE: Removes all rows and does not activate triggers. It is not usually logged on a row-by-row basis.



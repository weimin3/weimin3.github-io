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




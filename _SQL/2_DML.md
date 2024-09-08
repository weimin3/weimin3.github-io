---
title: "Data Manipulation Language(DML)"
collection: SQL
permalink: /SQL/DML
excerpt: 'Those commands are used to manipulate the data within the database,including SELECT,INSERT INTO,UPDATE,DELETE.DQL(Data Query Language)is in this part.'
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
## DQL
- Retrieve all columns from the employees table

```sql
SELECT * FROM employees;
```

- Retrieve specific columns
```sql
SELECT name,salary FROM employees;
```

- Filter data using `WHERE`
```sql
SELECT name,department FROM employees
WHERE salary > 50000;
```

- Sorting data using `ORDER BY`. `DESC`(descending order),`ASC`(ascending order)
```sql
SELECT name, salary FROM employees
ORDER BY salary DESC;
```

- Grouping data using `GROUP BY`
```sql
SELECT department, COUNT(*) AS total_employees
FROM employees
GROUP BY department;
```

- Filtering grouped data using `HAVING`
```sql
SELECT department, AVG(salary) AS average_salary
FROM employees
GROUP BY department
HAVING AVG(salary) > 50000;
```

- Joining two tables

**employee** table

| employee_id | employee_name | department_id |
|-------------|---------------|---------------|
| 1           | Alice         | 1             |
| 2           | Bob           | 2             |
| 3           | Charlie       | 2             |
| 4           | David         | NULL          |
| 5           | Eve           | 3             |

**departments** table

| department_id | department_name |
|---------------|-----------------|
| 1             | HR              |
| 2             | IT              |
| 3             | Marketing       |

    - INNER JOIN:Returns **only the matching records** from both tables.

    - LEFT JOIN:Returns **all records from the left table** and **the matching records from the right table**. If no match is found, NULL is returned.

    - RIGHT JOIN:Returns **all records from the right table** and **the matching records from the left table**. If no match is found, NULL is returned.

    - FULL OUTER JOIN：Returns **all records from both tables**, with NULL used to fill in unmatched records.

    - CROSS JOIN:Returns the Cartesian product of the two tables, i.e., all possible row combinations.

    - SELF JOIN:Joins a table to itself, **used to compare rows within the same table**.



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


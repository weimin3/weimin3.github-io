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
- **Retrieve all columns from the employees table**

```sql
SELECT * FROM employees;
```

- **Retrieve specific columns**
```sql
SELECT name,salary FROM employees;
```

- **Filter data using `WHERE`**
```sql
SELECT name,department FROM employees
WHERE salary > 50000;
```

- **Sorting data using `ORDER BY`.** `DESC`(descending order),`ASC`(ascending order)
```sql
SELECT name, salary FROM employees
ORDER BY salary DESC;
```

- **Grouping data using `GROUP BY`**
```sql
SELECT department, COUNT(*) AS total_employees
FROM employees
GROUP BY department;
```

- **Filtering grouped data using `HAVING`**
```sql
SELECT department, AVG(salary) AS average_salary
FROM employees
GROUP BY department
HAVING AVG(salary) > 50000;
```

- **Joining two tables**

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

    - **INNER JOIN:** Returns **only the matching records** from both tables.

    **Syntax**

    ```sql
    SELECT columns
    FROM table1
    INNER JOIN table2
    ON table1.column = table2.column;
    ```
    **Example**

    Only the employees with matching department_id in the departments table will be shown.

    ```sql
    SELECT employees.employee_name, departments.department_name
    FROM employees
    INNER JOIN departments
    ON employees.department_id = departments.department_id;
    ```

    - **LEFT JOIN:** Returns **all records from the left table** and **the matching records from the right table**. If no match is found, NULL is returned.

    **Syntax**

    ```sql
    SELECT columns
    FROM table1
    LEFT JOIN table2
    ON table1.column = table2.column;
    ```
    **Example**

    All employees will be returned, and unmatched departments will show NULL

    ```sql
    SELECT employees.employee_name, departments.department_name
    FROM employees
    LEFT JOIN departments
    ON employees.department_id = departments.department_id;
    ```

    - **RIGHT JOIN:** Returns **all records from the right table** and **the matching records from the left table**. If no match is found, NULL is returned.

    **Syntax**

    ```sql
    SELECT columns
    FROM table1
    RIGHT JOIN table2
    ON table1.column = table2.column;
    ```
    **Example**

    All departments will be shown, and unmatched employees will show NULL

    ```sql
    SELECT employees.employee_name, departments.department_name
    FROM employees
    RIGHT JOIN departments
    ON employees.department_id = departments.department_id;
    ```

    - **FULL OUTER JOIN：** Returns **all records from both tables**, with NULL used to fill in unmatched records.

    **Syntax**

    ```sql
    SELECT columns
    FROM table1
    FULL OUTER JOIN table2
    ON table1.column = table2.column;
    ```
    **Example**
 
    Returns all records from both employees and departments, with NULL for unmatched records.

    ```sql
    SELECT employees.employee_name, departments.department_name
    FROM employees
    FULL OUTER JOIN departments
    ON employees.department_id = departments.department_id;
    ```

    - **CROSS JOIN:** Returns the Cartesian product of the two tables, i.e., all possible row combinations.

    **Syntax**

    ```sql
    SELECT columns
    FROM table1
    CROSS JOIN table2;
    ```
    **Example**

    Returns every possible combination of rows from employees and departments

    ```sql
    SELECT employees.employee_name, departments.department_name
    FROM employees
    CROSS JOIN departments;
    ```

    - **SELF JOIN:** Joins a table to itself, **used to compare rows within the same table**.

    **Syntax**

    ```sql
    SELECT a.column1, b.column2
    FROM table a, table b
    WHERE a.column = b.column;
    ```
    **Example**

    Compares employees within the same department.

    ```sql
    SELECT e1.employee_name AS employee1, e2.employee_name AS employee2
    FROM employees e1
    JOIN employees e2
    ON e1.department_id = e2.department_id
    WHERE e1.employee_id <> e2.employee_id;
    ```
- **Limiting the number of rows returned**

**Syntax**
```sql
SELECT column1, column2, ...
FROM table_name
WHERE condition
LIMIT number_of_rows;
```

**Exmples**
    - Return the first 3 rows from the employees table

    ```sql
    SELECT employee_id, name
    FROM employees
    LIMIT 3;
    ```
    In SQL Server, the equivalent of `LIMIT` is `TOP`

    ```sql
    SELECT TOP 3 employee_id, name
    FROM employees;
    ```

    - Skip the first 5 rows and return the next 3 rows (rows 6, 7, and 8).

    ```sql
    SELECT employee_id, name
    FROM employees
    LIMIT 3 OFFSET 5;
    ````

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


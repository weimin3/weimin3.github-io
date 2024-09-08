---
title: "Data Definition Language(DDL)"
collection: SQL
category: Fundation
permalink: /SQL/DDL
excerpt: 'Those commands are used on the structure of database onjects like tables,indexes and schemas,including CREATE,ALTER,DROP,TRUNCATE.'
date: 2024-09-08
# venue: 'Journal 1'
# slidesurl: 'http://academicpages.github.io/files/slides1.pdf'
# paperurl: 'http://academicpages.github.io/files/paper1.pdf'
# citation: 'Your Name, You. (2009). &quot;Paper Title Number 1.&quot; <i>Journal 1</i>. 1(1).'
---
First, we can create a database, using the following syntax
```sql
CREATE DATABASE [IF NOT EXISTS] databasename;
```
If the database already exists, there will be an error if using `CREATE DATABASE databasename;` to create a database,instead we can use `CREATE DATABASE IF NOT EXISTS databasename;` to avoid this issue.

The following syntax is used to create a table:
```sql
CREATE TABLE table_name(
    column 1 datatype,
    column 2 datatype,
    column 3 datatype,
    ...
)
```
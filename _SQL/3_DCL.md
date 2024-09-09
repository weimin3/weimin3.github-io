---
title: "Data Control Language(DCL)"
collection: SQL
permalink: /SQL/DCL
excerpt: 'Those commands deal with the control of access to data in the database,cluding GRANT,REVOKE,DENY'
date: 2024-09-08
---
- [GRANT](#grant)
- [REVOKE](#revoke)
- [DENY](#deny)

Data Control Language (DCL) is used to control access to data within a database.These commands manage permissions for users and roles, specifying who can access or manipulate the data.
# GRANT
The command is used to give users or roles specific privileges on database objects (such as tables, views, or procedures).

**Syntax**
```sql
GRANT privilege_type ON object TO user_or_role;
```
**Example**

Grant SELECT and INSERT privileges on the employees table to user 'john'
```sql
GRANT SELECT, INSERT ON employees TO john;
```
# REVOKE
The command is used to remove or restrict the privileges granted to users or roles.

**Syntax**
```sql
REVOKE privilege_type ON object FROM user_or_role;
```
**Example**

Revoke the SELECT and INSERT privileges on the employees table from user 'john'
```sql
REVOKE SELECT, INSERT ON employees FROM john;
```
# DENY
The command is used to prevent users or roles from performing specific actions on database objects, regardless of any permissions that might have been granted.

**Syntax**
```sql
DENY privilege_type ON object TO user_or_role;
```
**Example**

Deny DELETE permission on the employees table to user 'john'.
```sql
DENY DELETE ON employees TO john;
```
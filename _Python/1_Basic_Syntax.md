---
title: "1. Basic Syntax"
collection: Python
permalink: /Python/basic-syntax/
date: 2024-09-08
---
# Literals

Literals refer to fixed values that appear directly in code.

```python
# Numeric literals
x = 10  

# String literal
name = "Alice"

# Boolean literal
is_active = True
```
In the code above, 10, "Alice", and "True" are all literals.

# Comments

Comments are used to explain the code. They help make the code more readable and understandable for others(or ourselves).

## Single-line Comments

Single-line comments start with a # symbol.
```python
# This is a single-line comment
x = 10  # This is another comment explaining x
```
## Multi-line Comments

Multi-line comments are typically used to explain larger sections of code, classes, or functions. They are enclosed in triple double-quotes (""").

This kind of multi-line comment is used to document a function or class.

```python
def add(a, b):
    """
    This function takes two arguments a and b
    and returns their sum.
    """
    return a + b
```

# Variables
Variables are used to store data that can be referenced and manipulated later.Python is dynamically typed, so don't need to declare the type of a variable explicitly.

**Format**
```python
variable_name = value
```

**Examples**
```python
x = 10  # x holds an integer
name = "Alice"  # name holds a string
is_active = True  # is_active holds a boolean
```
# `print()` Function

The print() function is used to output values to the console. Can pass multiple values separated by commas, and Python will print them in a sequence.

**Syntax:**
```python
print(value1, value2, value3, ...)
```
**Examples**
```python
name = "Alice"
age = 30
print("Name:", name, "Age:", age)
```
output:
```
Name: Alice Age: 30
```





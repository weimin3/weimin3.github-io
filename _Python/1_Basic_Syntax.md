---
title: "1. Basic Syntax"
collection: Python
permalink: /Python/basic-syntax/
date: 2024-09-08
---
- [Literals](#literals)
- [Comments](#comments)
  - [Single-line Comments](#single-line-comments)
  - [Multi-line Comments](#multi-line-comments)
- [Variables](#variables)
- [`print()` Function](#print-function)
- [Data Types](#data-types)
- [Type Conversion](#type-conversion)
- [Identifiers](#identifiers)
- [Operators](#operators)
  - [Arithmetic Operators](#arithmetic-operators)
  - [Assignment Operators](#assignment-operators)
- [String Definition](#string-definition)
- [String Concatenation](#string-concatenation)
- [String Formatting](#string-formatting)
  - [Placeholder Formatting](#placeholder-formatting)
  - [f-Strings](#f-strings)
- [`input()` function](#input-function)

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
In the code above, 10, "Alice", and True are all literals.

# Comments

Comments are used to explain the code. They help make the code more readable and understandable for others(or ourselves).

## Single-line Comments

Single-line comments start with a `#` symbol.
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
# Data Types

| **Type**     | **Description**              | **Examples**             |
|--------------|------------------------------|--------------------------|
| **Number**   | **Integer (int)**             | 10, -10                  |
|              | **Float (float)**             | 13.14, -13.14            |
|              | **Complex (complex)**         | 4 + 3j (ending with `j`) |
| **Boolean**  | Represents truth values       | `True`, `False`          |
| **String**   | Text-based data               | "Nice weather"           |
| **List**     | Ordered, mutable sequence     | `[1, 2, 3, "apple"]`     |
| **Tuple**    | Ordered, immutable sequence   | `(1, 2, 3, "banana")`    |
| **Set**      | Unordered, unique items       | `{1, 2, 3}`              |
| **Dictionary** | Unordered key-value pairs   | `{"name": "Alice", "age": 25}` |

The `type()` function is used to check the type of a value or variable in Python
```python
type(10)          # Output: <class 'int'>
type(13.14)       # Output: <class 'float'>
type("Hello")     # Output: <class 'str'>
```
# Type Conversion
`int(x)`: Converts x to an integer.
`float(x)`: Converts x to a floating-point number.
`str(x)`: Converts x to a string.

```python
int("123")      # Converts string "123" to integer 123
float("12.34")  # Converts string "12.34" to float 12.34
str(123)        # Converts integer 123 to string "123"
```
# Identifiers
Identifiers are names given to variables, classes, functions, or methods. 

Rules for Naming Identifiers:
- Identifiers can consist of Chinese characters, English letters, digits, and underscores.
- An identifier **cannot** begin with a digit.
- Identifiers are case-sensitive. For example, myVar and myvar are considered two different names.
- Cannot use reserved keywords in Python as identifiers (e.g., for, while, if, etc.).
  

Naming Conventions:
- Variable Names: Variable names should be descriptive and meaningful (i.e., they should make the purpose of the variable clear).
- Underscore Notation: Use underscores to separate words in variable names for readability.Example: `total_score`, `student_age`.
- Lowercase Letters: By convention, variable names are written in lowercase.
  
Invalid identifiers:
```python
2score = 80      # Invalid, starts with a digit
class = "Python" # Invalid, 'class' is a reserved keyword
```
# Operators

## Arithmetic Operators

Arithmetic Operators perform basic mathematical operations。

| Operator | Description   | Example   |
|----------|---------------|-----------|
| `+`      | Addition       | `1 + 2`   |
| `-`      | Subtraction    | `2 - 1`   |
| `*`      | Multiplication | `1 * 2`   |
| `/`      | Division       | `4 / 2`   |
| `//`     | Floor Division | `9 // 2` results in `4` |
| `%`      | Modulus        | `3 % 2` results in `1` |
| `**`     | Exponentiation | `10 ** 2` results in `100` |

## Assignment Operators
Assignment Operators are used to assign values to variables and perform operations in a single step。

| Operator | Description                | Example            |
|----------|----------------------------|--------------------|
| `=`      | Assignment                  | `num = 1`          |
| `+=`     | Addition Assignment         | `c += a` is equivalent to `c = c + a` |
| `-=`     | Subtraction Assignment      | `c -= a` is equivalent to `c = c - a` |
| `*=`     | Multiplication Assignment   | `c *= a` is equivalent to `c = c * a` |
| `/=`     | Division Assignment         | `c /= a` is equivalent to `c = c / a` |
| `%=`     | Modulus Assignment          | `c %= a` is equivalent to `c = c % a` |
| `**=`    | Exponentiation Assignment   | `c **= a` is equivalent to `c = c ** a` |
| `//=`    | Floor Division Assignment   | `c //= a` is equivalent to `c = c // a` |

# String Definition
In Python, strings can be defined using three different methods:
- 1. Single Quotes：this is useful for simple cases where the string does not contain any single quotes.`name = 'amy'`
- 2. Double Quotes: this is particularly useful if the string contains single quotes.`name = "Amy"`
- 3. Triple Quotes: this is useful when the string contains both single and double quotes, or spans multiple lines.`name = """Amy"""`


If the string itself contains single or double quotes, you can define the string in a way that avoids conflicts:
- Using Different Quotes:
  - If the string contains single quotes, define it with double quotes.
    ```python
    string_with_single_quote = "This is John's book."
    ```
  - If the string contains double quotes, define it with single quotes.
    ```python
    string_with_double_quote = 'He said, "Hello!"'
    ```
- Using Escape Characters
    ```python
    string_with_escape = "He said, \"Hello!\""
    ```

# String Concatenation
Strings can be concatenated using the `+` operator
```python
name = "Amy"
greeting = "Hello, " + name
print(greeting) 
# Output: Hello, Amy
```
**Note:** Strings cannot be directly concatenated with integers or floats. You need to convert non-string types to strings first.

# String Formatting
## Placeholder Formatting
- Basic Usage
  ```python
  name = "amy"
  print("My name is %s" % name)  # Output: My name is amy
  ```
- Multiple Variables
  ```python
  name = "amy"
  age = 18
  print("My name is %s, my age is %d" % (name, age))  # Output: My name is amy, my age is 18
  ```
- Precision Control
  ```python
  number = 10
  print("%5d" % number)  # Output: "   10" (width of 5 with leading spaces)

  pi = 3.14159
  print("%5.2f" % pi)  # Output: "  3.14" (width of 5 with 2 decimal places)
  ```
  - %5d specifies that the integer should be printed with a width of 5 characters, padding with spaces if necessary.
  - %5.2f specifies that the floating-point number should be printed with a width of 5 characters and 2 decimal places.

## f-Strings

f-strings (formatted string literals) provide a more readable and concise way to format strings
- Basic Usage
  ```python
  name = 'Amy'
  age = 18
  print(f"My name is {name}, age is {age}.")  
  # Output: My name is Amy, age is 18.
  ```
- Formatting Expressions
  ```python
  print(f"The result of 2 * 1 is：{2 * 1}")  
  # Output: The result of 2 * 1 is：2
  ```
# `input()` function
**Syntax:**
```python
variable_name = input("Prompt message")
```
The `input()` function is used to read a line of text from the user via the keyboard. The text provided in the function's argument is displayed as a prompt to the user.The data received from the `input()` function is always of type `str `(string), even if the user inputs numbers or other data types.

**Exercise**

Define two variables to capture input from the keyboard, with the following prompts:
```python
user_name = input("Please enter your name: ")
user_type = input("Please enter your user type (e.g., VIP): ")

print(f"Hello, {user_name}! You are a {user_type} user. Welcome to the program.")
```
If input "John" for the name and "VIP" for user type, the program will output:
```python
Hello, John! You are a VIP user. Welcome to the program.
```
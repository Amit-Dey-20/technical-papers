# Technical Report: PEP 8 Standards in Python

## 1. Introduction

PEP 8 is the official Python style guide. It provides guidelines for writing clean, readable, consistent, and maintainable Python code.

---

## 2. Indentation

Use 4 spaces for each level of indentation.

### Example

```
if age >= 18:
    print("Adult")
```

Avoid using tabs and spaces together.

---

## 3. Line Length

A line should generally contain a maximum of 79 characters.

### Example

```
student_name = "Amit"
student_age = 25
```

For comments and documentation, PEP 8 traditionally recommends keeping lines around 72 characters.

---

## 4. Naming Conventions

PEP 8 recommends meaningful and consistent names.

### 4.1 Variables and Functions

Use snake_case.

```
student_name = "Amit"

def calculate_total():
    pass
```

### 4.2 Constants

Use UPPER_CASE.

```
MAX_SIZE = 100
PI_VALUE = 3.14
```

### 4.3 Classes

Use PascalCase.

```
class StudentDetails:
    pass
```

### 4.4 Modules

Use lowercase names.

```
calculator.py
student.py
```

---

## 5. Blank Lines

Use blank lines to separate different sections of code.

### Example

```
import math


def calculate_area(radius):
    return math.pi * radius ** 2


area = calculate_area(5)
print(area)
```

Typically:

- 2 blank lines around top-level functions and classes.
- 1 blank line between methods inside a class when appropriate.

---

## 6. Imports

Imports should normally be placed at the top of the file.

### Example

```
import math
import os

from datetime import datetime
```

Avoid unnecessary imports.

---

## 7. Spaces Around Operators

Use spaces around operators.

### Correct

```
total = price + tax
result = number * 2
```

### Avoid

```
total=price+tax
result=number*2
```

---

## 8. Spaces After Commas

Use a space after commas.

### Correct

```
numbers = [10, 20, 30]
```

### Avoid

```
numbers = [10,20,30]
```

---

## 9. Comments

Comments should explain the code when necessary.

### Example

```
# Calculate the total price
total = price + tax
```

Comments should be clear, short, and relevant.

---

## 10. Docstrings

Use docstrings to describe functions, classes, and modules.

### Example

```
def calculate_square(number):
    """Return the square of a number."""
    return number ** 2
```

---

## 11. Comparisons

Use appropriate comparison operators.

### Example

```
if name == "Amit":
    print("Name matched")
```

For checking against "None", use "is" or "is not".

```
if value is None:
    print("No value")
```

---

## 12. Boolean Values

Use "True" and "False" directly when possible.

### Example

```
is_active = True

if is_active:
    print("Active")
```

---

## 13. Avoid Unnecessary Code

Write simple and readable code.

### Avoid

```
if is_valid == True:
    print("Valid")
```

### Prefer

```
if is_valid:
    print("Valid")
```

---

## 14. Exception Handling

Use specific exceptions instead of catching every exception.

### Prefer

```
try:
    number = int(input("Enter number: "))
except ValueError:
    print("Invalid number")
```

Avoid unnecessarily broad exception handling:

```
try:
    number = int(input("Enter number: "))
except:
    print("Error")
```

---

## 15. String Formatting

Use modern and readable string formatting.

### Example

```
name = "Amit"
age = 25

print(f"My name is {name} and I am {age} years old.")
```

---

## 16. Code Organization

A Python file should generally follow a clear structure:

```
Imports
   ↓
Constants
   ↓
Classes / Functions
   ↓
Main Program
```

### Example

```
import math

PI = math.pi


def calculate_area(radius):
    """Calculate the area of a circle."""
    return PI * radius ** 2


def main():
    area = calculate_area(5)
    print(area)


if __name__ == "__main__":
    main()
```


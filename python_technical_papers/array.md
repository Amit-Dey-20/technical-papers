
# 1. Introduction

An array is a data structure used to store multiple values in a single variable. Instead of creating separate variables for every value, an array allows us to store a collection of values together.

For example, instead of writing:

```python
student1 = "Amit"
student2 = "Rahul"
student3 = "Ankit"
```

we can store the values together:

```python
students = ["Amit", "Rahul", "Ankit"]
```

Python does not have a traditional built-in array data type like languages such as C or Java. In Python, lists are commonly used as arrays because they provide many operations for storing, accessing, modifying, searching, and sorting data.

Python also provides an array module for creating arrays containing elements of the same data type.

---

# 2. Arrays in Python

There are two common ways to work with array-like data in Python:

1. Python List
2. Python array module

## 2.1 List as an Array

A Python list can contain multiple elements and can store different data types.

```
numbers = [10, 20, 30, 40, 50]

print(numbers)
```

Output:

```
[10, 20, 30, 40, 50]
```

A list is commonly used as an array in Python because it is flexible and provides many built-in methods.

# 3. Important Points to Remember

    - Python lists are commonly used as arrays.
    - List indexes start from `0`.
    - Negative indexes can be used to access elements from the end.
    - `append()` adds one element at the end.
    - `insert()` adds an element at a specific position.
    - `extend()` adds multiple elements.
    - `remove()` removes the first matching value.
    - `pop()` removes an element using its index and returns it.
    - `clear()` removes all elements.
    -  `index()` finds the position of an element.
    -  `count()` counts occurrences of an element.
    -  `sort()` sorts the original list.
    -  `sorted()` creates a new sorted list.
    -  `reverse()` reverses the current order.
    -  `copy()` creates a shallow copy.
    -  `len()` returns the number of elements.
    -  `max()` returns the largest value.
    -  `min()` returns the smallest value.
    -  `sum()` calculates the total of numeric values.
    -  Slicing can be used to extract a portion of a list.
---
# 4. Example :-

The following program demonstrates several important array operations.

```
numbers = [30, 10, 50, 20, 40]

# Length
print("Length:", len(numbers))

# Add element
numbers.append(60)
print("After append:", numbers)

# Insert element
numbers.insert(1, 15)
print("After insert:", numbers)

# Remove element
numbers.remove(50)
print("After remove:", numbers)

# Sort
numbers.sort()
print("After sort:", numbers)

# Reverse
numbers.reverse()
print("After reverse:", numbers)

# Count
print("Count of 20:", numbers.count(20))

# Search
print("Index of 20:", numbers.index(20))

# Sum
print("Sum:", sum(numbers))

# Maximum
print("Maximum:", max(numbers))

# Minimum
print("Minimum:", min(numbers))
```

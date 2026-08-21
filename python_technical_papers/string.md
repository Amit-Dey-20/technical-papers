
# 1. Introduction

A string is a sequence of characters enclosed inside quotation marks. Strings are used to store and work with text in Python.

For example:

```python
name = "Amit"
```

A string can contain:

* Letters
* Numbers
* Special characters
* Spaces
* Symbols

Example:

```python
message = "Hello, Python!"
```

Strings are one of the most commonly used data types in Python. Python provides many built-in methods and operations for creating, accessing, modifying, searching, formatting, and processing strings.

# 2. Important String Methods

| Method         | Description                                                 |
| -------------- | ----------------------------------------------------------- |
| `upper()`      | Converts string to uppercase                                |
| `lower()`      | Converts string to lowercase                                |
| `capitalize()` | Capitalizes the first character                             |
| `title()`      | Capitalizes the first character of each word                |
| `swapcase()`   | Swaps uppercase and lowercase                               |
| `find()`       | Finds the first occurrence                                  |
| `rfind()`      | Finds the last occurrence                                   |
| `index()`      | Finds the first occurrence and raises an error if not found |
| `rindex()`     | Finds the last occurrence and raises an error if not found  |
| `count()`      | Counts occurrences                                          |
| `startswith()` | Checks starting text                                        |
| `endswith()`   | Checks ending text                                          |
| `replace()`    | Replaces text                                               |
| `split()`      | Splits a string into a list                                 |
| `join()`       | Joins iterable elements into a string                       |
| `strip()`      | Removes whitespace from both ends                           |
| `lstrip()`     | Removes whitespace from the left                            |
| `rstrip()`     | Removes whitespace from the right                           |
| `center()`     | Centers the string                                          |
| `ljust()`      | Left-aligns the string                                      |
| `rjust()`      | Right-aligns the string                                     |
| `zfill()`      | Adds zeros to the left                                      |
| `partition()`  | Splits around the first separator                           |
| `rpartition()` | Splits around the last separator                            |
| `translate()`  | Replaces characters using a translation table               |

---

# 3. Important String Checking Methods

| Method        | Purpose                                                 |
| ------------- | ------------------------------------------------------- |
| `isalpha()`   | Checks whether all characters are alphabetic            |
| `isdigit()`   | Checks whether all characters are digits                |
| `isdecimal()` | Checks whether all characters are decimal characters    |
| `isnumeric()` | Checks whether all characters are numeric               |
| `isalnum()`   | Checks whether all characters are alphabetic or numeric |
| `isspace()`   | Checks whether all characters are whitespace            |
| `islower()`   | Checks whether applicable characters are lowercase      |
| `isupper()`   | Checks whether applicable characters are uppercase      |
| `istitle()`   | Checks whether the string is title-cased                |

---

# 4. Complete String Operations Example

The following program demonstrates several important string operations.

```
text = "  Python Programming  "

# Length
print("Length:", len(text))

# Remove spaces
text = text.strip()
print("After strip:", text)

# Uppercase
print("Uppercase:", text.upper())

# Lowercase
print("Lowercase:", text.lower())

# Title case
print("Title:", text.title())

# Search
print("Index of Python:", text.find("Python"))

# Count
print("Count of Python:", text.count("Python"))

# Replace
print("After replace:", text.replace("Python", "Java"))

# Check starting text
print("Starts with Python:", text.startswith("Python"))

# Check ending text
print("Ends with Programming:", text.endswith("Programming"))

# Split
words = text.split()
print("Words:", words)

# Join
result = "-".join(words)
print("Joined:", result)
```


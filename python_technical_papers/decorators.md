# Introduction

A decorator is a function that allows us to modify or extend the behavior of another function without changing its original code.

Decorators are commonly used for:

- Logging
- Authentication
- Validation
- Timing
- Access control
- Code reuse

# Decorator Structure

A basic decorator generally follows this structure:

```
def decorator(function):

    def wrapper(*args, **kwargs):
        # Extra behavior

        result = function(*args, **kwargs)

        # Extra behavior

        return result

    return wrapper
```

The main components are:

- Decorator function
- Original function
- Wrapper function
- Extra behavior
- Calling the original function
- Returning the result

---

# Real-World Uses of Decorators

Decorators are commonly used for:

| Use            | Purpose                          |
| -------------- | -------------------------------- |
| Logging        | Record function calls            |
| Authentication | Check user access                |
| Authorization  | Check permissions                |
| Validation     | Validate input                   |
| Timing         | Measure execution time           |
| Caching        | Store previous results           |
| Debugging      | Track program behavior           |
| Rate Limiting  | Control function calls           |
| Error Handling | Handle exceptions                |
| Permissions    | Restrict access to functionality |

---

# Advantages of Decorators

Decorators provide several benefits:

- Code Reusability :– The same functionality can be applied to multiple functions.
- Less Repetition :– Common logic can be written once.
- Separation of Concerns :– Additional functionality can be separated from the    main function.
- Readability :– The `@decorator` syntax clearly shows additional behavior.
- Flexibility :– Functions can be modified without changing their original      implementation.

---

# Important Points to Remember

- A decorator modifies or extends a function's behavior.
- Functions in Python are first-class objects.
- A function can be passed as an argument.
- A function can return another function.
- A function defined inside another function is called a nested function.
- A higher-order function accepts or returns another function.
- The `@` symbol is used to apply a decorator.
- The wrapper function contains the additional behavior.
- `*args` handles positional arguments.
-  `**kwargs` handles keyword arguments.
-  The wrapper should return the original function's result when needed.
-  `functools.wraps` preserves function metadata.
-  Multiple decorators can be applied to one function.
-  Decorators can also accept parameters.
-  Classes can be used as decorators with `__call__()`.
-  Python provides built-in decorators such as `@property`, `@classmethod`, and `@staticmethod`.

---

# Important Decorator Concepts Summary

| Concept                 | Short Definition                                  |
| ----------------------- | ------------------------------------------------- |
| Function Object         | Functions can be stored and passed like values    |
| Nested Function         | Function defined inside another function          |
| Higher-Order Function   | Function that accepts or returns another function |
| Decorator               | Function that modifies another function           |
| Wrapper                 | Function that adds extra behavior                 |
| `@` Syntax              | Shortcut for applying a decorator                 |
| `*args`                 | Handles positional arguments                      |
| `**kwargs`              | Handles keyword arguments                         |
| `functools.wraps`       | Preserves original function metadata              |
| Multiple Decorators     | Applying more than one decorator                  |
| Parameterized Decorator | Decorator that accepts arguments                  |
| Class Decorator         | A class used as a decorator                       |
| `__call__()`            | Makes an object callable                          |
| `@property`             | Method accessed like an attribute                 |
| `@classmethod`          | Method that receives the class                    |
| `@staticmethod`         | Method without automatic `self` or `cls`          |
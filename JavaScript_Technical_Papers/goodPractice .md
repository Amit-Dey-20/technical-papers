# Some Good Practices

## Searching MDN

MDN Web Docs is a useful reference for JavaScript, HTML and CSS.

When you do not remember a method, search MDN instead of guessing.

 **Example**

Suppose you want to know how `Array.find()` works.

Search:

```text
MDN Array find
```

Look for the MDN page and check:

1. Syntax
2. Parameters
3. Return value
4. Examples
5. Browser/runtime compatibility
6. Related methods



## JavaScript Best Practices

- Indentation :- use consistent 2 or 4 spaces. Do not mix them.
- Variable naming :- use meaningful camelCase names.

```javascript
const studentName = "Amit";
const totalMarks = 450;
```

- Constants -> use `const` when the value will not be reassigned.
- Variables -> use `let` when the value needs to change.
- Avoid `var` -> prefer `let` and `const`.
- Loop variable naming -> use meaningful names instead of `i`, `j` when possible.

```javascript
for (const student of students) {
    console.log(student);
}
```

- Functions -> use descriptive names that explain what the function does.

```javascript
function calculateTotal() {
    // ...
}
```

- Boolean variables -> use names like `isActive`, `hasPermission`, `isValid`.
- Avoid magic numbers -> use named constants.

```javascript
const MAX_AGE = 100;
```

- Use `===` instead of `==`  for comparisons.
- Use comments only when they explain something that is not obvious.
- Keep functions small and focused on one task.
- Use spaces and line breaks to keep code readable.
- Avoid unnecessary code and duplicate logic.
- Use consistent quotation marks throughout the project.
- Follow PEP/ESLint-style coding standards and fix linting errors.
- Use meaningful file and function names so their purpose is clear.


## Passing Functions to Other Functions

In JavaScript, a function can be passed as an argument to another function and called when needed. Such a function is called a callback function.

```javascript
function greet(name) {
    console.log("Hello " + name);
}

function execute(callback) {
    callback("Amit");
}

execute(greet);
// Hello Amit
```

Here:

- `greet` is passed to `execute()`.
- `execute()` calls `greet()` when needed.
- This allows us to control when a function is executed.

Important:- Pass the function without `()` when you want to pass it.

```javascript
execute(greet);   // Pass function
execute(greet()); // Calls function immediately
```


## Named vs Anonymous Functions

- Named function -> has a function name and can be called using that name.
- Anonymous function -> does not have its own name and is usually assigned to a variable or passed as a callback.

### Named Function

```javascript
function greet() {
    console.log("Hello");
}

greet();
```

### Anonymous Function

```javascript
const greet = function() {
    console.log("Hello");
};

greet();
```

### Main difference

```text
Named function      -> has a name
Anonymous function  -> has no name
```

Named functions are useful when a function needs to be reused, while anonymous functions are commonly used as callbacks.


## Variable Number of Arguments

A function can accept a different number of arguments each time it is called.

In JavaScript, the rest parameter (`...`) is commonly used for this.

```javascript
function add(...numbers) {
    return numbers.reduce((sum, num) => sum + num, 0);
}

console.log(add(10, 20));       // 30
console.log(add(10, 20, 30));   // 60
console.log(add(10, 20, 30, 40)); // 100
```

- `...numbers` collects all arguments into an array.
- The function can receive any number of arguments.
- Useful when the number of inputs is not fixed.


## Debugging Strategies

Debugging means **finding and fixing errors in your code**.

- Read the error message -> it usually tells you what went wrong and where.
- Use `console.log()` -> check variable values and program flow.
- Use `console.error()` -> clearly show errors.
- Check one part at a time -> isolate where the problem occurs.
- Use breakpoints -> pause code execution and inspect values.
- Check variable types -> use `typeof` when unexpected values occur.
- Reproduce the error -> run the same code again to understand the problem.
- **Use browser DevTools / debugger -> inspect code, variables, and execution step by step.
- Check edge cases -> test empty arrays, `null`, `undefined`, zero, etc.
- Fix the cause, not just the symptom -> understand why the error happened before changing the code.

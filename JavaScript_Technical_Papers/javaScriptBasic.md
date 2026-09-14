# Javascript Basics 

## JavaScript Data Types

JavaScript has two main groups of data types: primitive and object types.

### Primitive types

```js
let name = "Amit";          // string
let age = 25;               // number
let isActive = true;        // boolean
let value;                  // undefined
let empty = null;           // null
let id = 123456789012345n;  // bigint
let key = Symbol("id");     // symbol
```

Primitive values are simple values. Strings, numbers, booleans, undefined, null, bigint, and symbol are primitive.

### Object type

Objects store collections of values.

```js
const user = {
    name: "Amit",
    age: 25
};

const numbers = [10, 20, 30];
```

Arrays and functions are also objects in JavaScript.

### Checking a type

```js
console.log(typeof "hello");  // "string"
console.log(typeof 10);       // "number"
console.log(typeof true);     // "boolean"
console.log(typeof undefined); // "undefined"
console.log(typeof null);     // "object"
```

`typeof null` returning `object` is an old JavaScript behavior.

## JavaScript Scopes

Scope decides where a variable can be accessed.

### Global scope
Variables declared Globally (outside any block or function) have Global Scope and it can be accessed from anywhere in a JavaScript program.

```js
const appName = "My App";

function showName() {
    console.log(appName);
}

showName();
```

`appName` can be used inside the function because it is in the outer scope.

### Function scope
All JavaScript functions have their own scope.

Variables defined inside a function are not accessible from outside the function.



```js
function test() {
    var message = "hello";
    console.log(message);
}

test();
// console.log(message); // Error
```

`var` is function-scoped.

### Block scope

Variables declared with `let` and `const` inside a code block are "block-scoped," meaning they are only accessible within that block.


```js
if (true) {
    let count = 10;
    const name = "Amit";
}

// count and name cannot be used here
```

A block is usually code inside `{ }`.

### Lexical scope

An inner function can access variables from its outer scope.

```js
function outer() {
    const message = "hello";

    function inner() {
        console.log(message);
    }

    inner();
}

outer();
```



## let, var and const

These keywords declare variables, but they behave differently.

| Keyword | Scope | Reassign | Redeclare |
|---|---|---|---|
| `let` | block | yes | no in same scope |
| `const` | block | no | no in same scope |
| `var` | function | yes | yes |



## Why We Must Not Use var

`var` is not usually preferred in modern JavaScript because its behavior can cause confusing bugs.

- It ignores block scope
- It allows redeclaration

### Rule

Use `const` first. Use `let` when reassignment is required. Avoid `var` unless working with old code that requires it.


## Why Global Variables Are Bad

- A global variable can be accessed from many places in a program.
- Any part of the program can change it.
- Bugs become harder to trace.
- Functions become dependent on outside state.
- Variable names can conflict.
- Testing becomes harder.


# Truthy and Falsy Values

JavaScript converts values to boolean in conditions.

## Falsy values

Common falsy values are:


- false
- 0
- ""
- null
- undefined
- NaN


## Truthy values

Except all the falsy values all are truthy values.




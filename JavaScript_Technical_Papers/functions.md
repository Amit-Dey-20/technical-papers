# Functions in Javascript

## Function Hoisting

Function declarations can be called before they appear in the code.

```js
sayHello();

function sayHello() {
    console.log("Hello");
}
```

This works because the function declaration is hoisted.

### Function expression

This does not work the same way:

```js
sayHello();

const sayHello = function () {
    console.log("Hello");
};
```

The variable exists in the temporal dead zone until its declaration is reached, so calling it early causes an error.




## What Happens When a Function Has No return

A function without a `return` statement returns `undefined`.

```js
function greet() {
    console.log("Hello");
}

const result = greet();

console.log(result); // undefined
```

Printing something is not the same as returning it.

```js
function add(a, b) {
    console.log(a + b);
}

const result = add(2, 3);

console.log(result); // undefined
```

Correct:

```js
function add(a, b) {
    return a + b;
}

console.log(add(2, 3)); // 5
```

Use `return` when the caller needs a value from the function.




## Different Ways of Declaring a Function

### 1. Function declaration

```js
function add(a, b) {
    return a + b;
}
```

Good for named reusable functions.

### 2. Function expression

```js
const add = function (a, b) {
    return a + b;
};
```

The function is stored in a variable.

### 3. Arrow function

```js
const add = (a, b) => {
    return a + b;
};
```

Short form:

```js
const add = (a, b) => a + b;
```

### 4. Anonymous function

A function without its own name:

```js
setTimeout(function () {
    console.log("Done");
}, 1000);
```

### 5. Named function expression

```js
const add = function addNumbers(a, b) {
    return a + b;
};
```

Giving a function a useful name can make debugging easier.


## Pass by Value and Pass by Reference

JavaScript always passes arguments by value. For objects, that value is a reference to the object.

### Primitive values

A copy of the value is passed.

```js
let age = 20;

function changeAge(value) {
    value = 30;
}

changeAge(age);

console.log(age); // 20
```

Changing `value` does not change `age`.

### Objects

The copied value is a reference to the same object.

```js
const user = {
    name: "Amit"
};

function changeName(person) {
    person.name = "John";
}

changeName(user);

console.log(user.name); // John
```

Both references point to the same object.


### Simple rule

Primitive: copied value.

Object: copied reference value, so object properties can be changed through that reference.








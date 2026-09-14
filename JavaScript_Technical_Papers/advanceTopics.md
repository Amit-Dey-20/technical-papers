# Advance Topics
## Spread Operator

The spread operator `...` expands values.

### Arrays

```js
const first = [1, 2];
const second = [3, 4];

const numbers = [...first, ...second];

console.log(numbers); // [1, 2, 3, 4]
```

### Copy an array

```js
const original = [1, 2, 3];
const copy = [...original];

copy.push(4);

console.log(original); // [1, 2, 3]
```

This creates a shallow copy.

### Objects

```js
const user = {
    name: "Amit",
    age: 25
};

const updatedUser = {
    ...user,
    age: 26
};
```

Later properties overwrite earlier properties.

### Function arguments

```js
const numbers = [10, 20, 30];

console.log(Math.max(...numbers)); // 30
```

Spread is useful for copying, combining and updating arrays/objects.






## Template Literals

Template literals use backticks.

```js
const name = "Amit";
const age = 25;

const message = `My name is ${name} and I am ${age} years old.`;

console.log(message);
```

They make string interpolation easier.

### Expressions

```js
const price = 100;
const quantity = 3;

console.log(`Total: ${price * quantity}`);
```

### Multiple lines

```js
const message = `Hello Amit,
Welcome to JavaScript.
`;
```

Use template literals when a string contains variables or expressions.











## Default Parameters

A default parameter is used when an argument is `undefined`.

```js
function greet(name = "Guest") {
    return `Hello ${name}`;
}

console.log(greet("Amit"));
console.log(greet());
```

Output:

```text
Hello Amit
Hello Guest
```

The default is used for `undefined`:

```js
function show(value = 10) {
    return value;
}

console.log(show(undefined)); // 10
console.log(show(null));      // null
```

Default parameters make functions safer and reduce repeated fallback code.



## Destructuring

Destructuring extracts values from arrays or properties from objects.

### Array destructuring

```js
const numbers = [10, 20, 30];

const [first, second] = numbers;

console.log(first);  // 10
console.log(second); // 20
```

### Object destructuring

```js
const user = {
    name: "Amit",
    age: 25
};

const { name, age } = user;

console.log(name);
console.log(age);
```

### Rename a property

```js
const { name: userName } = user;

console.log(userName);
```

### Default value

```js
const { city = "Bengaluru" } = user;
```

### Function parameters

```js
function showUser({ name, age }) {
    console.log(name, age);
}

showUser(user);
```

Destructuring is useful when only a few values are needed from a larger object or array.


## Closures

A closure happens when a function remembers variables from its outer scope even after the outer function has finished.

```js
function createCounter() {
    let count = 0;

    return function () {
        count++;
        return count;
    };
}

const counter = createCounter();

console.log(counter()); // 1
console.log(counter()); // 2
console.log(counter()); // 3
```

The returned function still has access to `count`.

### Why closures are useful

Closures can provide private state.

```js
function createAccount() {
    let balance = 0;

    return {
        deposit(amount) {
            balance += amount;
        },
        getBalance() {
            return balance;
        }
    };
}
```

Code outside cannot directly access `balance`.

Closures are common in callbacks, factories, event handlers and functional programming.


## Arrow Functions vs Regular Functions

 **Syntax**

Regular:

```js
function add(a, b) {
    return a + b;
}
```

Arrow:

```js
const add = (a, b) => a + b;
```

### this

Regular functions have their own `this` depending on how they are called.

Arrow functions do not create their own `this`. They use `this` from the surrounding scope.

```js
const user = {
    name: "Amit",

    regular() {
        console.log(this.name);
    },

    arrow: () => {
        console.log(this.name);
    }
};

user.regular(); // Amit
user.arrow();   // usually undefined in this context
```

### Constructor

Regular functions can be used with `new` when appropriate. Arrow functions cannot.

### Rule

Use arrow functions for short callbacks:

```js
numbers.map(number => number * 2);
```

Use regular methods/functions when you need normal `this` behavior or constructor behavior.




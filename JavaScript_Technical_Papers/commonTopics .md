# Common Topics:-

## Difference between == and ===

- `==` (Loose equality) -> compares values after type conversion.
- `===` (Strict equality) -> compares value and data type without conversion.

```javascript
5 == "5";    // true
5 === "5";   // false

5 == 5;      // true
5 === 5;     // true
```

Best practice:- Prefer `===` because it avoids unexpected type conversions.





## value === undefined vs !value

- `value === undefined` -> specifically checks whether the value is `undefined`.
- `!value` -> checks whether the value is **falsy**, so it can match many different values.

```javascript
let value;

value === undefined; // true
!value;              // true
```

But:

```javascript
let value = 0;

value === undefined; // false
!value;              // true

let value = "";

value === undefined; // false
!value;              // true
```

### Main difference

```text
value === undefined -> only checks for undefined
!value              -> checks for false, 0, "", null, undefined, NaN
```

So, use `value === undefined` when you specifically want to check for `undefined`.


## Array Utility Methods Chaining

Method chaining means using multiple array methods one after another on the same array.

```javascript
const numbers = [1, 2, 3, 4, 5];

const result = numbers
    .filter(num => num > 2)
    .map(num => num * 2);

console.log(result);
// [6, 8, 10]
```

Here:

```text
filter() -> [3, 4, 5]
map()    -> [6, 8, 10]
```

It makes code shorter and easier to read when multiple operations are needed.


## Difference between `null` and `undefined`

* `undefined` -> a variable has been declared but no value has been assigned.
* `null` -> represents an intentional empty value.

```javascript
let a;
console.log(a); // undefined

let b = null;
console.log(b); // null
```

### Main difference

```text
undefined -> value is not assigned
null      -> value is intentionally empty
```

## Importing and Exporting Modules using require and module.exports

Node.js uses modules to split code into different files.

### module.exports

Used to export a function, object, or value from a file.

```javascript
// math.js
function add(a, b) {
    return a + b;
}

module.exports = add;
```

### require()

Used to import the exported code into another file.

```javascript
// app.js
const add = require('./math');

console.log(add(2, 3));
// 5
```


## Console Methods

Console methods are used to display information in the browser or Node.js console.

- console.log() -> displays general information.
- console.error() -> displays an error message.
- console.warn() -> displays a warning message.
- console.info() -> displays informational messages.
- console.table() -> displays arrays or objects in a table.
- console.clear() -> clears the console.

```javascript
console.log("Hello");              // General output
console.error("Something went wrong"); // Error
console.warn("Be careful");        // Warning
console.info("User logged in");    // Information

console.table([10, 20, 30]);       // Table format
```

Most commonly used:-  `console.log()`, `console.error()`, and `console.warn()`.




# String

## Popular String Utility Methods

Strings are immutable in JavaScript. String methods return new strings instead of changing the original string.

```js
const text = "  JavaScript Basics  ";
```

### toUpperCase() / toLowerCase()

```js
console.log(text.toUpperCase());
console.log(text.toLowerCase());
```


### trim()

```js
console.log(text.trim()); // "JavaScript Basics"
```


### includes()

```js
console.log(text.includes("Script")); // true
```


### startsWith() / endsWith()

```js
console.log(text.startsWith("  Java")); // true
console.log(text.endsWith("  "));       // true
```

### slice()

```js
const word = "JavaScript";

console.log(word.slice(0, 4)); // Java
```

### replace()

```js
const message = "Hello Amit";

console.log(message.replace("Amit", "John"));
```

### split()

Converts a string into an array.

```js
const csv = "red,green,blue";

console.log(csv.split(","));
// ["red", "green", "blue"]
```

### concat()

```js
console.log("Hello".concat(" ", "World"));
```


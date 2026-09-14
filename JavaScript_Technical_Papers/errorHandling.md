# Error Handling

## Error Handling with try and catch

`try catch` a program handle an error without immediately stopping the whole operation.

```js
try {
    const data = JSON.parse("wrong json");
    console.log(data);
} 
catch (error) {
    console.error("Could not parse JSON");
}
```

### finally

`finally` runs whether an error happened or not.

```js
try {
    console.log("Start");
}
catch (error) {
    console.error(error);
} finally {
    console.log("Finished");
}
```

### Why catch is useful

Without a suitable catch, an error may stop the current execution path.

A catch block can:

- show a useful message
- log debugging information
- clean up resources
- recover when recovery is possible

Do not silently ignore errors.

Bad:

```js
try {
    riskyOperation();
} catch (error) {
}
```

Better:

```js
try {
    riskyOperation();
} catch (error) {
    console.error("Operation failed:", error);
}
```

## Throwing Errors

Use `throw` when the program reaches an invalid state and the caller needs to handle it.

```js
function divide(a, b) {
    if (b === 0) {
        throw new Error("Cannot divide by zero");
    }

    return a / b;
}
```

Handle it:

```js
try {
    console.log(divide(10, 0));
} catch (error) {
    console.error(error.message);
}
```

### Error object vs string

Prefer:

```js
throw new Error("Invalid age");
```

over:

```js
throw "Invalid age";
```

An `Error` object has useful information such as `message` and `stack`.

```js
try {
    throw new Error("Something went wrong");
} catch (error) {
    console.log(error.message);
    console.log(error.stack);
}
```

Throw errors that describe what actually went wrong.


## Reading Error Messages and Stack Traces

Reading the error message and stack trace is one of the most important debugging skills.

Example:

```js
function calculateTotal(price, quantity) {
    return price * quantity;
}

function checkout() {
    return calculateTotal(100, undefined);
}

console.log(checkout());
```

The result may expose an unexpected value. If an actual runtime error occurs, the stack trace usually shows:

1. Error type
2. Error message
3. File name
4. Line and column
5. Function call path

Example style:

```text
TypeError: Cannot read properties of undefined
    at calculateTotal (app.js:2:18)
    at checkout (app.js:6:12)
    at app.js:9:13
```

Start at the error message. Then open the first useful file/line in your own code. Follow the call chain backward.

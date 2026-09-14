# Loops

## Different Types of for Loops

### for with numbers

Use it when you need the index or controlled counting.

```js
for (let i = 0; i < 5; i++) {
    console.log(i);
}
```

### for...in

Used mainly for object keys.

```js
const user = {
    name: "Amit",
    age: 25
};

for (const key in user) {
    console.log(key, user[key]);
}
```

Avoid using `for...in` for normal array iteration because it iterates keys and can include inherited properties.

### for...of

Used for iterable values such as arrays and strings.

```js
const numbers = [10, 20, 30];

for (const number of numbers) {
    console.log(number);
}
```

### forEach

```js
numbers.forEach(function (number) {
    console.log(number);
});
```

Good for performing an action for every item.

## while

Useful when the number of iterations depends on a condition.

```js
let count = 0;

while (count < 3) {
    console.log(count);
    count++;
}
```

Choose the loop based on what you need: index/control, keys, values, callback execution, or condition-based repetition.

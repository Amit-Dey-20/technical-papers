# Arrays

## Popular Array Utility Methods

### pop()

Removes the last element.

Mutable

```javascript
const arr = [1, 2, 3];
arr.pop();

console.log(arr); // [1, 2]
```

### push()

Adds elements to the end.

Mutable

```javascript
const arr = [1, 2];
arr.push(3);

console.log(arr); // [1, 2, 3]
```

### concat()

Combines arrays and returns a new array.

Immutable

```javascript
const arr = [1, 2];
const result = arr.concat([3, 4]);

console.log(result); // [1, 2, 3, 4]
```

### slice()

Returns a portion of an array.

Immutable

```javascript
const arr = [1, 2, 3, 4];
const result = arr.slice(1, 3);

console.log(result); // [2, 3]
```

### splice()

Adds, removes, or replaces elements.

Mutable

```javascript
const arr = [1, 2, 3];
arr.splice(1, 1);

console.log(arr); // [1, 3]
```

### join()

Converts array elements into a string.

Immutable

```javascript
const arr = ["A", "B", "C"];

console.log(arr.join("-")); // A-B-C
```

### flat()

Removes nested array levels.

Immutable

```javascript
const arr = [1, [2, 3]];

console.log(arr.flat()); // [1, 2, 3]
```

## Finding

- find() -> returns the first matching element.
- indexOf() -> returns the index of a value.
- includes() -> returns true/false if a value exists.
- findIndex() -> returns the index of the first matching element.



```javascript
const numbers = [10, 20, 30, 40];

numbers.find(x => x > 20);        // 30
numbers.indexOf(20);              // 1
numbers.includes(20);             // true
numbers.findIndex(x => x > 20);   // 2
```

All are immutable (do not change the original array).

## Higher Order Functions

- forEach() -> runs a function for each element. Immutable
- filter() -> returns elements that match a condition. Immutable
- map() -> creates a new array by transforming elements. Immutable
- reduce() -> reduces an array to a single value. Immutable
- sort() -> sorts the array. Mutable (changes original array)


```javascript
const numbers = [10, 20, 30, 40];

numbers.forEach(x => console.log(x));
// 10
// 20
// 30
// 40

numbers.filter(x => x > 20);
// [30, 40]

numbers.map(x => x * 2);
// [20, 40, 60, 80]

numbers.reduce((sum, x) => sum + x, 0);
// 100

numbers.sort((a, b) => a - b);
// [10, 20, 30, 40]
```

**Note:** `sort()` changes the original array, while the others do not.

### forEach vs map, filter and reduce

Use `forEach` when the goal is an action for every item.

```js
const names = ["Amit", "John"];

names.forEach(name => {
    console.log(name);
});
```

Use `map` when you need a new array with transformed values.

```js
const prices = [100, 200];

const withTax = prices.map(price => price * 1.18);
```

Use `filter` when you need only matching items.

```js
const ages = [15, 20, 25];

const adults = ages.filter(age => age >= 18);
```

Use `reduce` when many values need to become one result.

```js
const prices = [100, 200, 300];

const total = prices.reduce((sum, price) => sum + price, 0);
```


## Array Methods Chaining

Method chaining means using the result of one array method as the input to another.

Example:

```js
const numbers = [1, 2, 3, 4, 5, 6];

const result = numbers
    .filter(number => number % 2 === 0)
    .map(number => number * 10)
    .reduce((total, number) => total + number, 0);

console.log(result); // 120
```

Chaining is useful when each step has one clear job.

Avoid very long chains that become difficult to understand. Split them into variables when readability improves.



# Objects

## Popular Object Utility Methods

JavaScript provides useful static methods through `Object`.

```js
const user = {
    name: "Amit",
    age: 25
};
```

### Object.keys

Returns an array of keys.

```js
console.log(Object.keys(user));
// ["name", "age"]
```

Immutable with respect to `user`.

### Object.values

Returns an array of values.

```js
console.log(Object.values(user));
// ["Amit", 25]
```

### Object.entries

Returns key-value pairs.

```js
console.log(Object.entries(user));
// [["name", "Amit"], ["age", 25]]
```

### Object.assign

Copies properties into a target object and mutates the target.

```js
const target = {};
Object.assign(target, user);

console.log(target);
```

### Object.fromEntries

Creates an object from key-value pairs.

```js
const entries = [
    ["name", "Amit"],
    ["age", 25]
];

const user = Object.fromEntries(entries);

console.log(user);
```

## Object.freeze

Prevents changes to an object at the top level.

```js
const settings = {
    theme: "dark"
};

Object.freeze(settings);
```

`Object.keys`, `values`, `entries`, and `fromEntries` create new results. `Object.assign` changes its target object.

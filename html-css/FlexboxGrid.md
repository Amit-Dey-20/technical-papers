# Flexbox and Grid

Flexbox and Grid are CSS layout systems used to arrange elements on a webpage.

* Flexbox :- mainly for one direction: row or column.
* Grid :- for rows and columns.

---

# 1. Flexbox

To use Flexbox:

```css
.container {
    display: flex;
}
```

## Flexbox Container Properties

These properties are applied to the parent/container.

### flex-direction

Controls the direction of items.

```css
.container {
    flex-direction: row;
}
```

Values:

```text
row
row-reverse
column
column-reverse
```

### flex-wrap

Controls whether items move to a new line.

```css
.container {
    flex-wrap: wrap;
}
```

Values:

```text
nowrap
wrap
wrap-reverse
```

### flex-flow

Shorthand for flex-direction and flex-wrap.

```css
.container {
    flex-flow: row wrap;
}
```

### justify-content

Aligns items along the main axis.

```css
.container {
    justify-content: center;
}
```

Common values:

```text
flex-start
flex-end
center
space-between
space-around
space-evenly
```

### align-items

Aligns items along the cross axis.

```css
.container {
    align-items: center;
}
```

Common values:

```text
flex-start
flex-end
center
stretch
baseline
```

### align-content

Controls the alignment of multiple flex lines.

It works when flex-wrap: wrap creates multiple lines.

```css
.container {
    align-content: center;
}
```

Common values:

```text
flex-start
flex-end
center
space-between
space-around
space-evenly
stretch
```

### gap

Creates space between flex items.

```css
.container {
    gap: 20px;
}
```

We can also use:

```css
row-gap: 10px;
column-gap: 20px;
```

---

# Flexbox Item Properties

These properties are applied to the children/items.

### order

Changes the order of an item.

```css
.item {
    order: 2;
}
```

The default value is:

```css
order: 0;
```

A higher value appears later.

### flex-grow

Controls how much an item can grow when extra space is available.

```css
.item {
    flex-grow: 1;
}
```

### flex-shrink

Controls how much an item can shrink when there is not enough space.

```css
.item {
    flex-shrink: 1;
}
```

The default value is 1.

### flex-basis

Sets the initial size of an item before extra space is distributed.

```css
.item {
    flex-basis: 200px;
}
```


### align-self

Overrides align-items for one particular item.

```css
.item {
    align-self: center;
}
```

---

# 2. CSS Grid

Grid is used to create layouts using rows and columns.

To use Grid:

```css
.container {
    display: grid;
}
```

# Grid Container Properties

These properties are applied to the parent/container.

### grid-template-columns

Defines the columns.

```css
.container {
    grid-template-columns: 1fr 1fr 1fr;
}
```

This creates three equal columns.

### grid-template-rows

Defines the rows.

```css
.container {
    grid-template-rows: 100px 200px;
}
```

### grid-template-areas

Gives names to different areas of the grid.

```css
.container {
    grid-template-areas:
        "header header"
        "main sidebar"
        "footer footer";
}
```

### gap

Creates space between grid items.

```css
.container {
    gap: 20px;
}
```

we can also use:

```css
row-gap: 10px;
column-gap: 20px;
```

### justify-items

Aligns grid items horizontally inside their grid cells.

```css
.container {
    justify-items: center;
}
```

Common values:

```text
start
end
center
stretch
```

### align-items

Aligns grid items vertically inside their grid cells.

```css
.container {
    align-items: center;
}
```

### place-items

Shorthand for:

```text
align-items + justify-items
```

Example:

```css
.container {
    place-items: center;
}
```

### justify-content

Aligns the whole grid horizontally inside the container when extra space is available.

```css
.container {
    justify-content: center;
}
```

### align-content

Aligns the whole grid vertically inside the container when extra space is available.

```css
.container {
    align-content: center;
}
```

### place-content

Shorthand for:

```text
align-content + justify-content
```

Example:

```css
.container {
    place-content: center;
}
```

---

# Grid Item Properties

These properties are applied to the grid children/items.

### grid-column

Controls which columns an item occupies.

```css
.item {
    grid-column: 1 / 3;
}
```

The item occupies columns 1 and 2.

### grid-row

Controls which rows an item occupies.

```css
.item {
    grid-row: 1 / 3;
}
```

The item occupies rows 1 and 2.

---
## References
1. https://youtu.be/tN12g5QUIqg?si=CvSretEP_KAuJPrv
2. https://css-tricks.com/snippets/css/a-guide-to-flexbox/
3. https://youtu.be/byCsxHUuOrk?si=cmn14sO7xtf9vgyY
4. https://css-tricks.com/complete-guide-css-grid-layout/

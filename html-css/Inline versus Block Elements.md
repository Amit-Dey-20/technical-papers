# Inline vs Block Elements

## Introduction

HTML elements are mainly divided into two types:

1. Block-level elements
2. Inline elements

## Block-level Elements

Block elements start on a new line and usually take the full available width.

Examples:

```html
<div>Block element</div>
<p>Paragraph</p>
<h1>Heading</h1>
```

Example:

```html
<div>First</div>
<div>Second</div>
```

Output:

```text
First
Second
```

Common block elements:

```html
<div>
<p>
<h1> to <h6>
<section>
<header>
<footer>
```

## Inline Elements

Inline elements do not start on a new line. They take only the space they need.

Examples:

```html
<span>First</span>
<span>Second</span>
```

Output:

```text
First Second
```

Common inline elements:

```html
<span>
<a>
<strong>
<em>
<b>
<i>
```

## Main Difference

### Block
- Starts on a new line.
- Usually takes full width.
- Width and height can be set.
- Example: `<div>`

### Inline
- Stays on the same line
- Takes only required width
- Width and height generally don't apply normally
- Example: `<span>`                          

## Example

```html
<div>Block 1</div>
<div>Block 2</div>

<span>Inline 1</span>
<span>Inline 2</span>
```

Result:

```text
Block 1
Block 2

Inline 1 Inline 2
```

## References
1. https://www.w3schools.com/html/html_blocks.asp
2. https://www.geeksforgeeks.org/html/html-block-and-inline-elements/

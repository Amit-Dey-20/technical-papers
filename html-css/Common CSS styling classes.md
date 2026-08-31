# Common CSS Styling Classes

## Introduction

CSS classes are reusable styles that can be applied to HTML elements.

A class is created using `.` before the class name.

## Common Text Classes

```css
.text-center {
    text-align: center;
}

.text-bold {
    font-weight: bold;
}

.text-left {
    text-align: left;
}

.text-right {
    text-align: right;
}
```

## Common Spacing Classes

```css
.mt-10 {
    margin-top: 10px;
}

.mb-10 {
    margin-bottom: 10px;
}

.p-10 {
    padding: 10px;
}
```

Naming:

```text
m -> margin
p -> padding
t -> top
b -> bottom
l -> left
r -> right
```

## Common Display Classes

```css
.d-block {
    display: block;
}

.d-inline {
    display: inline;
}

.d-flex {
    display: flex;
}

.d-grid {
    display: grid;

}

.d-none {
    display: none;
}
```

## Common Flexbox Classes

```css
.flex-row {
    flex-direction: row;
}

.flex-column {
    flex-direction: column;
}

.justify-center {
    justify-content: center;
}

.align-center {
    align-items: center;
}
```

## Common Other Classes

```css
.w-full {
    width: 100%;
}

.h-full {
    height: 100%;
}

.rounded {
    border-radius: 5px;
}

.border {
    border: 1px solid black;
}
```

## Important Note

These are common class naming conventions, not built-in CSS classes.

They help make CSS reusable, consistent, and easy to maintain.

Frameworks such as Bootstrap and Tailwind CSS provide their own predefined utility classes.

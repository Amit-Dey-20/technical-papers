# CSS Positioning

## Introduction

The position property is used to control the position of an HTML element.

The main values are:

1. static
2. relative
3. absolute
4. fixed
5. sticky

## 1. Position: Static

static is the default position of an element.

```css
.box {
    position: static;
}
```

The element stays in the normal document flow.

top, right, bottom, and left do not work with static.

## 2. Position: Relative

position: relative moves an element from its normal position.

Example:

```css
.box {
    position: relative;
    top: 20px;
    left: 30px;
}
```

The element moves:

- 20px down from its original position
- 30px to the right from its original position

The original space of the element is still maintained.

## 3. Position: Absolute

position: absolute removes the element from the normal document flow.

Example:

```css
.box {
    position: absolute;
    top: 20px;
    left: 30px;
}
```

The element is positioned relative to its nearest positioned ancestor.

Usually, we make the parent:

```css
.parent {
    position: relative;
}
```

And the child:

```css
.child {
    position: absolute;
    top: 0;
    right: 0;
}
```

Here, .child is positioned relative to .parent.

## 4. Position: Fixed

position: fixed positions an element relative to the viewport.

The element stays in the same position even when the page is scrolled.

Example:

```css
.navbar {
    position: fixed;
    top: 0;
    left: 0;
}
```

It is commonly used for:

- Fixed navigation bars
- Floating buttons
- Chat buttons

## 5. Position: Sticky

position: sticky behaves like relative until the element reaches a specified position while scrolling.

After reaching that position, it sticks there.

Example:

```css
.heading {
    position: sticky;
    top: 0;
}
```

It is commonly used for:

- Sticky headers
- Navigation bars
- Section headings

## Top, Right, Bottom and Left

These properties are used to control the position of positioned elements.

```css
.box {
    position: relative;
    top: 20px;
    right: 10px;
    bottom: 10px;
    left: 20px;
}
```

They specify the distance from the corresponding side.

For example:

```css
.box {
    position: absolute;
    top: 20px;
    right: 20px;
}
```

The element is placed 20px from the top and 20px from the right of its containing block.

## Relative vs Absolute

### Relative

- Stays in normal document flow
- Original space is maintaine
- Moves from its normal position
- Can act as a reference for absolute children

## Absolute

- Removed from normal document flow
- Original space is not maintained
- Positioned using top, right, bottom, or left
- Usually positioned relative to a positioned parent

## References
1. https://www.w3schools.com/css/css_position.asp
2. https://youtu.be/9BlNJFIMUrY?si=iRD8qBQo9ueRcCOE
3. https://developer.mozilla.org/en-US/docs/Web/CSS/Reference/Properties/position
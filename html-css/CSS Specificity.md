# CSS Specificity

## What is CSS Specificity?

CSS Specificity is the rule used by the browser to decide which CSS rule should be applied when multiple rules target the same element.

Higher specificity = higher priority.

---

## Specificity Order

```text
Inline > ID > Class/Attribute/Pseudo-class > Element/Pseudo-element > Universal
````

| Selector                  | Specificity |
| ------------------------- | ----------- |
| Inline                    | (1,0,0,0)   |
| ID #id                    | (0,1,0,0)   |
| Class .class              | (0,0,1,0)   |
| Attribute [type]          | (0,0,1,0)   |
| Pseudo-class :hover       | (0,0,1,0)   |
| Element p                 | (0,0,0,1)   |
| Pseudo-element ::before   | (0,0,0,1)   |
| Universal *               | (0,0,0,0)   |

---

### Example

```css
p {
    color: blue;
}

.msg {
    color: green;
}

#text {
    color: red;
}
```

Specificity:

```text
p      -> (0,0,0,1)
.msg   -> (0,0,1,0)
#text  -> (0,1,0,0)
```

Therefore:

```text
#text wins -> red
```

---

##  Element Selector

Element selectors have low specificity.

```css
p {
    color: blue;
}
```

---

## Class Selector

Class selectors have higher specificity than element selectors.

```css
.text {
    color: green;
}
```

---

## ID Selector

ID selectors have higher specificity than class selectors.

```css
#title {
    color: red;
}
```

---

## Inline CSS

Inline CSS has higher specificity than ID, class, and element selectors.

```html
<p id="title" style="color: orange;">
    Hello
</p>
```

The text will be orange.

---

## Multiple Selectors

Specificity increases when selectors are combined.

```css
p.text {
    color: green;
}
```

Here:

- p -> element
- .text -> class

So p.text is more specific than just .text.

---

## Same Specificity

If two rules have the same specificity, the rule written last wins.

```css
.text {
    color: blue;
}

.text {
    color: red;
}
```

Result: Red

---

## !important

!important gives a declaration very high priority.

```css
p {
    color: red !important;
}
```

Use !important only when necessary because it can make CSS difficult to maintain.

---

## References
- https://www.w3schools.com/css/css_specificity.asp
- https://developer.mozilla.org/en-US/docs/Web/CSS/Guides/Cascade/Specificity

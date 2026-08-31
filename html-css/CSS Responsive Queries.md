# CSS Responsive Queries

## What are Responsive Queries?

**Responsive Queries** in CSS are mainly done using Media Queries.

Media queries help us make a website look good on different screen sizes, such as:

- Mobile
- Tablet
- Laptop 
- Desktop

---

## 1. Basic Syntax

```css
@media (condition) {
    /* CSS styles */
}
```

### Example

```css
@media (max-width: 600px) {
    body {
        background-color: lightblue;
    }
}
```

This means:

If the screen width is 600px or less, the background becomes light blue.

---

## 2. max-width

max-width applies styles when the screen is smaller than or equal to the given width.

```css
@media (max-width: 600px) {
    .box {
        width: 100%;
    }
}
```

Useful for mobile devices.

---

## 3. min-width

min-width applies styles when the screen is larger than or equal to the given width.

```css
@media (min-width: 768px) {
    .box {
        width: 50%;
    }
}
```

---

## 4. Responsive Example

### HTML

```html
<div class="box">
    Hello World
</div>
```

### CSS

```css
.box {
    width: 50%;
    background-color: yellow;
}

/* Mobile */
@media (max-width: 600px) {
    .box {
        width: 100%;
    }
}
```

On a large screen:

```text
Box -> 50% width
```

On a small screen:

```text
Box -> 100% width
```

---

## Why Use Media Queries?

Media queries help us:

- Make websites mobile-friendly
- Change element sizes
- Change layouts
- Hide or show elements
- Adjust font sizes
- Improve user experience

### Note

Media queries allow CSS to change based on the screen size or device conditions.

## References
1. https://youtu.be/tcgXPI6Nxsw?si=Skjv1Ui4bf2bpaBK
2. https://css-tricks.com/a-complete-guide-to-css-media-queries/

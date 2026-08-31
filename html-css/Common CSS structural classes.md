# Common CSS Structural Classes

## Introduction

Structural classes are common class names used to organize the structure and layout of a webpage.

They are not built-in CSS classes. Developers create them based on the needs of the webpage.

Common structural classes include:

- container
- header
- nav
- main
- section
- content
- sidebar
- footer

## 1. Container

container is used to hold and control the main content of a page.

```html
<div class="container">
    Content
</div>
```

```css
.container {
    width: 80%;
    margin: auto;
}
```

It can be used to control the width and alignment of content.

## 2. Header

header is used for the top part of a webpage.

```html
<div class="header">
    Website Header
</div>
```

It usually contains:

- Logo
- Website name
- Navigation

## 3. Navigation

nav is used for navigation links.

```html
<div class="nav">
    <a href="#">Home</a>
    <a href="#">About</a>
    <a href="#">Contact</a>
</div>
```

## 4. Main

main is used for the main content of the webpage.

```html
<div class="main">
    Main content
</div>
```

## 5. Section

section is used to divide content into different sections.

```html
<div class="section">
    <h2>About Us</h2>
    <p>About our website.</p>
</div>
```

## 6. Content

content is commonly used for the main area that contains information.

```html
<div class="content">
    <p>This is the main content.</p>
</div>
```

## 7. Sidebar

sidebar is used for additional content placed beside the main content.

```html
<div class="sidebar">
    <p>Related links</p>
</div>
```

It can contain:

- Links
- Menus
- Categories
- Additional information

## 8. Footer

footer is used for the bottom part of a webpage.

```html
<div class="footer">
    Copyright 2026
</div>
```

It commonly contains:

- Copyright information
- Contact information
- Links
- Social media links

## Example Structure

A common webpage structure can look like this:

```html
<div class="container">

    <div class="header">
        Header
    </div>

    <div class="nav">
        Navigation
    </div>

    <div class="main">

        <div class="content">
            Main Content
        </div>

        <div class="sidebar">
            Sidebar
        </div>

    </div>

    <div class="footer">
        Footer
    </div>

</div>
```

## Summary

These class names are conventions. You can choose different names, but using clear and meaningful names makes CSS easier to understand and maintain.

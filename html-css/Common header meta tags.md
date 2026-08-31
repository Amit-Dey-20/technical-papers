# Common Header Meta Tags

## Introduction

Meta tags provide information about an HTML page to the browser and search engines.

They are written inside the `<head>` section.

## 1. Charset

Defines the character encoding of the webpage.

```html
<meta charset="UTF-8">
```

UTF-8 supports most characters and symbols.

## 2. Viewport

Makes the webpage responsive on different screen sizes.

```html
<meta name="viewport" content="width=device-width, initial-scale=1.0">
```

- width=device-width -> uses the device's screen width.
- initial-scale=1.0 -> sets the initial zoom level.

## 3. Description

Provides a short description of the webpage.

```html
<meta name="description" content="Learn HTML and CSS basics.">
```

Search engines may use this description in search results.

## 4. Keywords

Provides keywords related to the webpage.

```html
<meta name="keywords" content="HTML, CSS, JavaScript">
```

Modern search engines generally do not use this tag for ranking.

## 5. Author

Specifies the author of the webpage.

```html
<meta name="author" content="John Doe">
```

## 6. Robots

Tells search engine crawlers how to handle the page.

```html
<meta name="robots" content="index, follow">
```

Common values:

```text
index
noindex
follow
nofollow
```

## 7. Theme Color

Sets the theme color used by some browsers and devices.

```html
<meta name="theme-color" content="#ffffff">
```

## Example

A basic `<head>` section can contain:

```html
<head>
    <meta charset="UTF-8">

    <meta name="viewport"
          content="width=device-width, initial-scale=1.0">

    <meta name="description"
          content="Learn HTML and CSS basics.">

    <meta name="author"
          content="John Doe">

    <title>HTML and CSS</title>
</head>
```
## References
1. https://www.w3schools.com/tags/tag_meta.asp
2. https://www.geeksforgeeks.org/websites-apps/10-most-important-meta-tags-for-seo/

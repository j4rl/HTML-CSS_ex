# CSS Basics

CSS (Cascading Style Sheets) controls how HTML is presented. It handles colors, spacing, typography, layout, and visual states.

## CSS Syntax

CSS rules consist of a selector and a declaration block.

```css
selector {
  property: value;
}
```

- `selector`: The HTML element or group of elements to style, such as `p`, `.card`, or `#main-title`.
- `property`: The CSS feature to change, such as `color` or `font-size`.
- `value`: The chosen value for the property, such as `red` or `1rem`.

## Selectors

Selectors define which HTML elements the CSS rules apply to.

### Element Selector

Targets all instances of an element.

```css
p {
  color: blue;
}
```

### Class Selector

Targets elements with a specific class.

```css
.my-class {
  color: green;
}
```

### ID Selector

Targets a single element with a specific ID.

```css
#my-id {
  color: red;
}
```

### Attribute Selector

Targets elements with a specific attribute.

```css
[type="text"] {
  border: 1px solid blue;
}
```

### Descendant Selector

Targets elements that are inside another element.

```css
div p {
  color: purple;
}
```

### Child Selector

Targets direct children of an element.

```css
div > p {
  color: orange;
}
```

### Pseudo-classes and Pseudo-elements

Pseudo-classes target a state. Pseudo-elements target a specific part of an element.

```css
a:hover {
  color: red;
}

p::first-line {
  font-weight: bold;
}
```

- Pseudo-classes: `:hover`, `:focus`, `:nth-child()`, `:first-child`, `:last-child`, `:not()`.
- Pseudo-elements: `::before`, `::after`, `::first-letter`, `::first-line`.

## Common CSS Properties

### Text and Font

- `color`: Text color.
- `font-family`: Font family.
- `font-size`: Size of the font.
- `font-weight`: Thickness of the font, such as `normal` or `bold`.
- `text-align`: Text alignment, such as `left`, `center`, or `right`.
- `text-decoration`: Text decoration, such as `underline` or `line-through`.
- `line-height`: Space between lines of text.

### Box Model

- `width`: Width of an element.
- `height`: Height of an element.
- `margin`: Space outside an element.
- `padding`: Space inside an element.
- `border`: Border around an element.
- `box-sizing`: How width and height are calculated, such as `content-box` or `border-box`.

### Background

- `background-color`: Background color of an element.
- `background-image`: Background image of an element.
- `background-size`: Size of the background image, such as `cover` or `contain`.
- `background-position`: Position of the background image, such as `center` or `top right`.
- `background-repeat`: Whether the background image repeats, such as `no-repeat` or `repeat`.

### Positioning and Display

- `position`: Positioning method, such as `static`, `relative`, `absolute`, `fixed`, or `sticky`.
- `top`, `right`, `bottom`, `left`: Offsets for positioned elements.
- `display`: Display type, such as `block`, `inline`, `inline-block`, `flex`, `grid`, or `none`.
- `float`: Floats an element to the left or right. Prefer Flexbox or Grid for most layouts.
- `clear`: Controls how floating elements affect following content.

## Examples

### Basic Reset

```css
*,
*::before,
*::after {
  box-sizing: border-box;
}

body {
  margin: 0;
  min-height: 100dvh;
}

html {
  scroll-behavior: smooth;
}
```

### Basic Page Styling

```css
body {
  font-family: Arial, sans-serif;
  line-height: 1.6;
  background-color: #f4f4f4;
  color: #333;
  padding: 20px;
}

h1 {
  color: #555;
}

a {
  color: #0066cc;
}

a:hover,
a:focus {
  text-decoration-thickness: 0.15em;
}
```

### Using a Web Font

Prefer loading fonts with a `<link>` element in HTML for performance:

```html
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Roboto:wght@400;700&display=swap" rel="stylesheet">
```

Then use the font in CSS:

```css
body {
  font-family: "Roboto", Arial, sans-serif;
}
```

## Additional Resources

- [MDN Web Docs - CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
- [CSS-Tricks](https://css-tricks.com/)
- [W3Schools - CSS](https://www.w3schools.com/css/)
- [Can I use...](https://caniuse.com/) - Check browser support for CSS features.

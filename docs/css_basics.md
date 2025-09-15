# CSS Basics
This document provides a concise overview of CSS (Cascading Style Sheets) basics, including syntax, selectors, properties, and common practices.
## CSS Syntax
CSS rules consist of a selector and a declaration block.
```css
selector {
  property: value;
}
```
- `selector`: HTML element(s) to style (e.g., `p`, `.class`, `#id`).
- `property`: CSS property to change (e.g., `color`, `font-size`).
- `value`: Value for the property (e.g., `red`, `16px`).    
## Selectors
Selectors define which HTML elements the CSS rules apply to.
- **Element Selector**: Targets all instances of an element.
  ```css
  p {
    color: blue;
  }
  ```   
- **Class Selector**: Targets elements with a specific class.
  ```css
  .my-class {
    color: green;
  }
    ```
- **ID Selector**: Targets a single element with a specific ID.
  ```css
  #my-id {
    color: red;
  }
  ```   
- **Attribute Selector**: Targets elements with a specific attribute.
  ```css
  [type="text"] {
    border: 1px solid blue;
  }
  ```
- **Descendant Selector**: Targets elements that are descendants of a specified element.
  ```css
  div p {
    color: purple;
  } 
    ```
- **Child Selector**: Targets direct children of a specified element.
  ```css    
  div > p {
    color: orange;
  }
  ```       
- **Pseudo-classes**: Targets elements in a specific state.
  ```css
  a:hover {
    color: red;
  }
  ```
- **Pseudo-elements**: Targets specific parts of an element.
  ```css
  p::first-line {
    font-weight: bold;
  }
  ```
  **List of pseudo classes and elements**
    - Pseudo-classes: `:hover`, `:focus`, `:nth-child()`, `:first-child`, `:last-child`, `:not()`, etc.
    - Pseudo-elements: `::before`, `::after`, `::first-letter`, `::first-line`, etc.
## Common CSS Properties
- **Text and Font**:
    - `color`: Text color.
    - `font-family`: Font type.
    - `font-size`: Size of the font.
    - `font-weight`: Thickness of the font (e.g., `normal`, `bold`).
    - `text-align`: Alignment of text (e.g., `left`, `center`, `right`).
    - `text-decoration`: Decoration of text (e.g., `underline`, `line-through`).
    - `line-height`: Space between lines of text.
- **Box Model**:
    - `width`: Width of an element.
    - `height`: Height of an element.
    - `margin`: Space outside an element.
    - `padding`: Space inside an element.
    - `border`: Border around an element.
    - `box-sizing`: How width and height are calculated (e.g., `content-box`, `border-box`).
- **Background**:
    - `background-color`: Background color of an element.   
    - `background-image`: Background image of an element.
    - `background-size`: Size of the background image (e.g., `cover`, `contain`).
    - `background-position`: Position of the background image (e.g., `center`, `    top right`).
    - `background-repeat`: Whether the background image repeats (e.g., `no-repeat`, `repeat`).
- **Positioning and Display**:
    - `position`: Positioning method (e.g., `static`, `relative`, `absolute`, `fixed`).
    - `top`, `right`, `bottom`, `left`: Offsets for positioned elements.
    - `display`: Display type (e.g., `block`, `inline`, `inline-block`, `none`).
    - `float`: Float an element to the left or right.
    - `clear`: Control the behavior of floating elements.
---
## A few examples 
**Resetting a page**
```css
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
body{
    height: 100dvh;
}
html{
    scroll-behavior: smooth;
}
``` 
**Basic styling for a webpage**
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
  text-decoration: none;
}
a:hover {
  text-decoration: underline;
}
``` 
**Importing and using a Google Font**
```css
@import url('https://fonts.googleapis.com/css2?family=Roboto:wght@400;700&display=swap');

body {
  font-family: 'Roboto', sans-serif;
}   
``` 
---
## Additional Resources
- [MDN Web Docs - CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
- [CSS-Tricks](https://css-tricks.com/)
- [W3Schools - CSS](https://www.w3schools.com/css/)
- [Can I use...](https://caniuse.com/) - Check browser support for CSS features.


# Flexbox & Grid Layout
This section covers the fundamentals of CSS Flexbox and Grid layout systems, which are essential for creating responsive and flexible web designs. It includes explanations, code examples, and best practices to help you understand how to use these powerful layout techniques effectively.
## Flexbox Layout
Flexbox (Flexible Box Layout) is a one-dimensional layout model that allows you to arrange items in a row or column, with flexible sizing and alignment.
**Container Properties:**
```css
.container {
  display: flex; /* or inline-flex */
  flex-direction: row; /* row | row-reverse | column | column-reverse */
  flex-wrap: nowrap; /* nowrap | wrap | wrap-reverse */
  justify-content: flex-start; /* flex-start | flex-end | center | space-between | space-around | space-evenly */
  align-items: stretch; /* stretch | flex-start | flex-end | center | baseline */
  align-content: stretch; /* stretch | flex-start | flex-end | center | space-between | space-around */
}
``` 
**Item Properties:**
```css
.item {
  flex: 1; /* grow | shrink | basis */
  align-self: auto; /* auto | flex-start | flex-end | center | baseline | stretch */
}
```
**Flexbox Usage**:
```html
<div class="container">
  <div class="item">Item 1</div>
  <div class="item">Item 2</div>
  <div class="item">Item 3</div>
</div>
``` 
- The container uses `display: flex;` to enable Flexbox layout.
- Items inside the container will be arranged in a row by default.      
- You can control the alignment and spacing of items using the container properties.
- Each item can have its own flex properties to control how it grows or shrinks within the container.
**CSS for the above example**:
```css
.container {
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  align-items: center;
}

.item {
  flex: 1;
  padding: 10px;
  border: 1px solid #ccc;
  margin: 5px;
}
``` 
- This will create a horizontal layout with three items spaced evenly across the container.
- Each item will grow equally to fill the available space.  
- You can change `flex-direction` to `column` to stack items vertically.
- Use `flex-wrap: wrap;` to allow items to wrap onto multiple lines if they exceed the container width.
- Flexbox is particularly useful for creating responsive layouts that adapt to different screen sizes.
### Flexbox Best Practices
- Use Flexbox for one-dimensional layouts (either row or column).
- Combine Flexbox with media queries for responsive designs.
- Use `flex-grow`, `flex-shrink`, and `flex-basis` to control item sizing.
- Avoid using fixed widths on flex items to maintain flexibility.
- Test layouts in different browsers to ensure compatibility.
- Use developer tools to inspect and modify Flexbox properties in real-time for debugging and fine-tuning layouts.
- Remember that Flexbox is not suitable for complex two-dimensional layouts; use CSS Grid for those scenarios.

## CSS Grid Layout
CSS Grid is a two-dimensional layout system that allows you to create complex grid-based layouts with rows and columns.
To enable Grid layout, set the `display` property of a container to `grid` or `inline-grid`.
**Container Properties:**
```css
.container {
  display: grid; /* or inline-grid */
  grid-template-columns: repeat(3, 1fr); /* defines 3 equal columns */
  grid-template-rows: auto; /* defines rows based on content */
  grid-gap: 10px; /* space between grid items */
}
```
**Item Properties:**
```css
.item {
  grid-column: span 1; /* default: span 1 column */
  grid-row: span 1; /* default: span 1 row */
}
```
**Grid Usage**:
```html
<div class="container">
  <div class="item">Item 1</div>
  <div class="item">Item 2</div>
  <div class="item">Item 3</div>
</div>
```
- The container uses `display: grid;` to enable Grid layout.
- Items inside the container will be arranged in a grid with three equal columns.
- You can control the size and spacing of items using the container properties.
- Each item can span multiple rows or columns using the item properties.
**CSS for the above example**:
```css
.container {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  grid-gap: 10px;
}

.item {
  padding: 10px;
  border: 1px solid #ccc;
}
```
- This will create a grid layout with three columns and a 10px gap between items.
- Each item will occupy one grid cell by default.
- You can change `grid-template-columns` to create different column layouts (e.g., `1fr 2fr 1fr` for varying widths).
- Use `grid-template-rows` to define row heights (e.g., `100px 200px auto`).
- CSS Grid is ideal for creating complex layouts that require both rows and columns.
### Grid magic
- Use `grid-area` to name grid areas and place items more intuitively.  
  - The `grid-area` property can be used to assign a name to a grid item, which can then be referenced in the `grid-template-areas` property of the container.
    ```css
    .item1 {
      grid-area: header;
    }
    .item2 {
      grid-area: sidebar;
    }
    .item3 {
      grid-area: content;
    }
    .item4 {
      grid-area: footer;
    }
    .container {
      display: grid;
      grid-template-areas:
        "header header header"
        "sidebar content content"
        "footer footer footer";
      grid-gap: 10px;
    }
    ```
    - This allows for a more semantic and readable way to define the layout of grid items.
- Use `minmax()` to create flexible grid tracks that adapt to content size.
  - The `minmax()` function allows you to define a grid track that has a minimum and maximum size.
    ```css
    .container {
      display: grid;
      grid-template-columns: repeat(3, minmax(100px, 1fr));
      grid-gap: 10px;
    }
    ```
    - This ensures that each column will be at least 100px wide but can grow to fill available space.   
- Use `auto-fit` and `auto-fill` with `repeat()` to create responsive grids that adjust the number of columns based on available space.
  - `auto-fit` will collapse empty tracks, while `auto-fill` will maintain them.
    ```css
    .container {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(150px, 1fr));
      grid-gap: 10px;
    }
    ```
    - This creates a responsive grid that automatically adjusts the number of columns based on the container's width.   
- Masonry-like layouts can be achieved using CSS Grid by allowing items to span multiple rows and columns.
  - You can create a masonry-like layout by allowing grid items to span multiple rows or columns based on their content size.
    ```css
    .item1 {
      grid-column: span 2;
      grid-row: span 2;
    }
    .item2 {
      grid-column: span 1;
      grid-row: span 1;
    }
    .item3 {
      grid-column: span 1;
      grid-row: span 2;
    }
    .container {
      display: grid;
      grid-template-columns: repeat(3, 1fr);
      grid-auto-rows: 100px; /* base row height */
      grid-gap: 10px;
    }
    ```
    - This allows for a more dynamic and visually interesting layout where items can vary in size.      
### Grid Best Practices
- Use CSS Grid for two-dimensional layouts (both rows and columns).
- Combine Grid with media queries for responsive designs.
- Use named grid areas for better readability and maintainability.  
- Avoid using fixed sizes on grid tracks to maintain flexibility.
- Test layouts in different browsers to ensure compatibility.   
- Use developer tools to inspect and modify Grid properties in real-time for debugging and fine-tuning layouts.
- Remember that CSS Grid is not suitable for simple one-dimensional layouts; use Flexbox for those scenarios.
- Use CSS Grid for overall page layout and Flexbox for components within the grid.
## When to use Flexbox vs Grid
- Use Flexbox for simpler, one-dimensional layouts where items are arranged in a single row or column.
- Use CSS Grid for more complex, two-dimensional layouts that require both rows and columns.    
- Combine both Flexbox and Grid in your designs to leverage the strengths of each layout system.
- Use Flexbox for components that need to be flexible and adapt to content size, such as navigation bars or card layouts.
- Use CSS Grid for overall page layout, such as defining header, sidebar, main content, and footer areas.
- Experiment with different combinations to achieve the desired layout and design for your web pages.
- Use CSS media queries to adjust Flexbox and Grid properties for different screen sizes and devices.
- Always test your layouts in different browsers to ensure compatibility and consistency.

---

## A few examples
**Basic Flexbox Layout**
```css
.container {
  display: flex;
  flex-direction: row;
  justify-content: space-around;
  align-items: center;
}
.item {
  flex: 1;
  padding: 20px;
  border: 1px solid #ccc;
  margin: 10px;
}
```
**HTML for the above example**:
```html
<div class="container">
  <div class="item">Item 1</div>
  <div class="item">Item 2</div>
  <div class="item">Item 3</div>
</div>
```
- This creates a horizontal layout with three items spaced evenly across the container.
- Each item will grow equally to fill the available space.  
- Change `flex-direction` to `column` to stack items vertically.    
- Use `flex-wrap: wrap;` to allow items to wrap onto multiple lines if they exceed the container width.
```**Basic CSS Grid Layout**
```css  
.container {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  grid-gap: 15px;
}
.item {
  padding: 20px;
  border: 1px solid #ccc;
}
```
**HTML for the above example**:
```html
<div class="container">
  <div class="item">Item 1</div>
  <div class="item">Item 2</div>
  <div class="item">Item 3</div>
  <div class="item">Item 4</div>
  <div class="item">Item 5</div>
</div>
```
- This creates a grid layout with four equal columns and a 15px gap between items.
- Each item will occupy one grid cell by default.
- Change `grid-template-columns` to create different column layouts (e.g., `1fr 2fr 1fr` for varying widths).
- Use `grid-template-rows` to define row heights (e.g., `100px 200px auto`).
- Use `grid-auto-rows` to set a base row height for automatic rows.
- CSS Grid is ideal for creating complex layouts that require both rows and columns.
```
**Combining Flexbox and Grid**
```css
.page {
  display: grid;
  grid-template-areas:
    "header header header"
    "sidebar content content"
    "footer footer footer";
  grid-gap: 10px;
}   
.header {
  grid-area: header;
  background: #f4f4f4;
  padding: 20px;
}
.sidebar {
  grid-area: sidebar;
  background: #ccc;
  padding: 20px;
}
.content {
  grid-area: content;
  display: flex;
  flex-direction: column;
  gap: 10px;
}
.footer {
  grid-area: footer;
  background: #f4f4f4;
  padding: 20px;
}
``` 
**HTML for the above example**:
```html
<div class="page">
  <div class="header">Header</div>
  <div class="sidebar">Sidebar</div>
  <div class="content">
    <div class="item">Content Item 1</div>
    <div class="item">Content Item 2</div>
    <div class="item">Content Item 3</div>
  </div>
  <div class="footer">Footer</div>
</div>
```
- This creates a page layout using CSS Grid for the overall structure and Flexbox for the content area.
- The header, sidebar, content, and footer are defined as grid areas.
- The content area uses Flexbox to arrange its items in a column with spacing between them.
- This combination allows for a flexible and responsive design that leverages the strengths of both layout systems
- Use media queries to adjust the layout for different screen sizes.
---
## Additional Resources
- [A Complete Guide to Flexbox - CSS-Tricks](https://css-tricks.com/snippets/css/a-guide-to-flexbox/)
- [A Complete Guide to Grid - CSS-Tricks](https://css-tricks.com/snippets/css/complete-guide-grid/)
- [MDN Web Docs - Flexbox](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Flexible_Box_Layout/Basic_Concepts_of_Flexbox)
- [MDN Web Docs - CSS Grid](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Grid_Layout)
- [Flexbox Froggy - A game for learning Flexbox](https://flexboxfroggy.com/)
- [Grid Garden - A game for learning CSS Grid](https://cssgridgarden.com/)

---

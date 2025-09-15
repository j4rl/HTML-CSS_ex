# Performance, Organization & Best Practices
This section covers best practices for writing efficient, maintainable, and high-performance HTML and CSS code. It includes tips on optimizing loading times, organizing stylesheets, and ensuring accessibility.   
How to plan and structure your HTML and CSS for better performance and maintainability is also discussed.
## Performance Optimization
- Minimize HTTP requests by combining CSS files and using CSS sprites for images.
- Use external stylesheets to leverage browser caching.
- Minify CSS files to reduce file size.
- Use shorthand properties in CSS to reduce code size.  
```css
/* Shorthand example */
margin: 10px 15px 20px 25px; /* top right bottom left */
/* instead of */
margin-top: 10px;
margin-right: 15px;
margin-bottom: 20px;
margin-left: 25px;
```
- Load CSS in the `<head>` to prevent rendering delays.
- Use media queries to load styles only for specific devices or screen sizes.
- Avoid using `@import` in CSS as it can delay loading.
- Optimize images and use modern formats like WebP. 
- Use `font-display: swap;` for web fonts to improve text visibility during font loading.
```css
@font-face {
  font-family: 'MyFont';
  src: url('myfont.woff2') format('woff2');
  font-display: swap;
}
```
- Limit the use of complex selectors and deep nesting in CSS to improve rendering performance.
- Use CSS variables for repeated values to reduce redundancy and improve maintainability.
```css
:root {
  --main-bg-color: #f0f0f0;
  --main-text-color: #333;
}
body {
  background-color: var(--main-bg-color);
  color: var(--main-text-color);
}
```
## Organization and Maintainability
- Use a consistent naming convention for classes and IDs (e.g., BEM - Block Element Modifier).
  - Example of BEM:
```html
<div class="card">
    <h2 class="card__title">Title</h2>
    <p class="card__description">Description</p>
    <button class="card__button card__button--primary">Click Me</button>
</div>
```
  - Example of another convention (kebab-case):
```html 
<div class="nav-bar">
    <ul class="nav-bar__list">
        <li class="nav-bar__item"><a href="#" class="nav-bar__link">Home</a></li>
        <li class="nav-bar__item"><a href="#" class="nav-bar__link">About</a></li>
    </ul>
</div>
```
  -Example of camelCase:
```html
<div class="navBar">
    <ul class="navBarList">
        <li class="navBarItem"><a href="#" class="navBarLink">Home</a></li>
        <li class="navBarItem"><a href="#" class="navBarLink">About</a></li>
    </ul>
</div>
```
- Separate layout styles from component styles in CSS files.
- Use comments in CSS to explain sections and complex rules.
```css
/* Layout styles */
.container {
  display: flex;
  flex-direction: column;
}
/* Component styles */
.button {
    background-color: blue;
    color: white;
    }
    ``` 
- Group related CSS rules together.
- Use a CSS preprocessor (like SASS or LESS) for larger projects to enable nesting, variables, and mixins.
- Regularly audit and clean up unused CSS rules.
- Use a CSS linter to enforce coding standards and catch errors.
- Document your CSS architecture and conventions for team projects.
## Accessibility Best Practices
- Use semantic HTML elements (e.g., `<header>`, `<nav>`, `<main>`, `<footer>`, `<article>`, `<section>`) to improve accessibility and SEO.
- Ensure sufficient color contrast between text and background. 
- Use relative units (like `em`, `rem`, `%`) for font sizes to improve scalability.
- Provide `alt` attributes for images to describe their content.
- Use ARIA roles and properties to enhance accessibility for dynamic content.
- Ensure that interactive elements (like buttons and links) are keyboard accessible.    
- Use focus styles to indicate which element is focused when navigating via keyboard.
```css
button:focus, a:focus {
  outline: 2px solid blue;
  outline-offset: 2px;
}
```
- Test your site with screen readers and other assistive technologies.
- Use tools like Lighthouse, Axe, or WAVE to audit accessibility.
  - Links to tools:
    - [Lighthouse](https://developers.google.com/web/tools/lighthouse)
    - [Axe](https://www.deque.com/axe/)
    - [WAVE](https://wave.webaim.org/)

## General Best Practices
- Keep CSS files modular and organized by feature or component.
- Avoid inline styles; use classes and IDs instead.
- Use a version control system (like Git) to manage changes and collaborate with others.
- Regularly review and refactor your CSS to improve performance and maintainability.
- Stay updated with the latest CSS features and best practices by following web development blogs and resources.
- Test your website across different browsers and devices to ensure compatibility.
- Use developer tools in browsers to inspect and debug CSS issues.
- Always consider the user experience (UX) when designing and coding your web pages.
- Optimize for mobile first, then enhance for larger screens.
- Use CSS Grid and Flexbox for layout instead of older methods like floats and positioning.
- Avoid using `!important` in CSS as it makes debugging and maintenance harder.
- Use CSS custom properties (variables) for theming and easier updates.
- Regularly back up your code and use a staging environment for testing changes before deploying to production.
- Document your CSS architecture and conventions for team projects.
- Use a CSS linter to enforce coding standards and catch errors.
  - Links to linters:
    - [Stylelint](https://stylelint.io/)
    - [CSSLint](https://csslint.net/)
- Keep your CSS DRY (Don't Repeat Yourself) by reusing classes and styles.
- Use meaningful class names that describe the purpose of the element.
- Avoid deep nesting of selectors to keep specificity low and maintainable.

- Use a consistent indentation style (e.g., 2 spaces or 4 spaces) for better readability.
- Regularly audit and clean up unused CSS rules using tools like PurgeCSS or UnCSS.
  - Links to tools:
    - [PurgeCSS](https://purgecss.com/)
    - [UnCSS](https://uncss-online.com/)
- Always test your website's performance using tools like Google PageSpeed Insights or GTmetrix.
  - Links to tools:
    - [Google PageSpeed Insights](https://developers.google.com/speed/pagespeed/insights/)
    - [GTmetrix](https://gtmetrix.com/)
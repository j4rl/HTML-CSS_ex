# Responsive Design & Media Queries
Responsive web design ensures that web pages look good and function well on a variety of devices and screen sizes. Media queries are a key tool in achieving this by allowing you to apply different CSS styles based on the characteristics of the device, such as its width, height, orientation, and resolution.
Sometimes you can achieve responsiveness using flexible layouts, images, and CSS properties like `flexbox` and `grid`, but media queries provide more control for specific breakpoints.
## Media Queries
Media queries are used in CSS to apply styles conditionally based on the characteristics of the device or viewport. The most common use case is to adjust styles based on the width of the viewport.
**Basic Syntax:**
```css
@media (condition) {
  /* CSS rules here */
}
```
- `condition`: A media feature like `max-width`, `min-width`, `orientation`, etc.
**Example:**
```css  
@media (max-width: 600px) {
  body {
    background-color: lightblue;
  }
}
@media (min-width: 601px) and (max-width: 1200px) {
  body {
    background-color: lightgreen;
  }
}
@media (min-width: 1201px) {
  body {
    background-color: lightcoral;
  }
}
``` 
- The first block applies when the viewport width is 600px or less.
- The second block applies when the width is between 601px and 1200px.
- The third block applies when the width is 1201px or more.
**Common Media Features:**
- `width` and `height`: Width and height of the viewport.
- `orientation`: The orientation of the device (portrait or landscape).
- `resolution`: The resolution of the device (e.g., `min-resolution: 300dpi`).  
- `aspect-ratio`: The ratio of width to height (e.g., `min-aspect-ratio: 16/9`).
- `hover`: Whether the primary input mechanism can hover over elements (e.g., `hover: hover`).
- `pointer`: The accuracy of the primary input mechanism (e.g., `pointer: fine`).
**Combining Conditions:**
```css
@media (min-width: 600px) and (hover: hover) {
  /* Styles for devices with a minimum width of 600px and hover capability */
}   
@media (max-width: 800px), (orientation: portrait) {
  /* Styles for devices with a maximum width of 800px or in portrait orientation */
}
```
- Use `and` to combine multiple conditions that must all be true.
- Use `,` (comma) to create an "or" condition where any of the conditions can be true.
## Special word on creating media queries for printing
You can also create media queries specifically for print styles using the `print` media type. This is useful for optimizing the layout and appearance of web pages when they are printed.
**Example:**
```css
@media print {
  body {
    font-size: 12pt;
    color: black;
    background: white;
  }
  .no-print {
    display: none;
  }
}
```
- The styles inside this block will only apply when the page is printed.    
- The `.no-print` class can be used to hide elements that should not appear in the printed version.
## Best Practices
- Start with a mobile-first approach: Write your base styles for small screens first, then use media queries to add styles for larger screens.
- Use relative units (like `em`, `rem`, `%`) instead of fixed units (like `px`) for widths, margins, and paddings to enhance flexibility.
- Test your designs on multiple devices and screen sizes to ensure a consistent user experience.
- Keep media queries organized and grouped logically in your CSS for easier maintenance.
- Avoid overusing media queries; aim for a fluid design that adapts well without needing too many breakpoints.
- Use tools like browser developer tools to simulate different screen sizes and test your media queries.
- Consider accessibility and readability when designing for different screen sizes.
- Remember that media queries can also be used in HTML with the `<link>` element to load different stylesheets based on conditions.
**Example:**
```html
<link rel="stylesheet" href="styles.css" media="(min-width: 600px)">    
<link rel="stylesheet" href="mobile.css" media="(max-width: 599px)">
```
**Contents of the files:**
- `styles.css`: Styles for screens 600px and wider.
- `mobile.css`: Styles for screens 599px and narrower.

**Performance Considerations**
- This approach can help in loading only the necessary CSS for the device, improving performance.   
- Always keep performance in mind; avoid loading large images or resources for small screens where they are not needed.
- Use `min` and `max` attributes to set minimum and maximum values for numeric inputs.
- Use `step` to define the increment step for numeric inputs.

## Width and Height
Here is how you can use `min-width`, `max-width`, `min-height`, and `max-height` in media queries:
```css
@media (min-width: 600px) {
  /* Styles for screens wider than 600px */
}
@media (max-width: 599px) {
  /* Styles for screens narrower than 600px */
}
@media (min-height: 400px) {
  /* Styles for screens taller than 400px */
}
@media (max-height: 399px) {
  /* Styles for screens shorter than 400px */
}
```
- `min-width` and `max-width`: Apply styles based on the minimum and maximum width of the viewport.
- `min-height` and `max-height`: Apply styles based on the minimum and maximum height of the viewport.
## Orientation  
You can use the `orientation` media feature to apply styles based on whether the device is in portrait or landscape mode.
```css
@media (orientation: portrait) {
  /* Styles for portrait orientation */
}
@media (orientation: landscape) {
  /* Styles for landscape orientation */
}
```
- `portrait`: The height is greater than or equal to the width.
- `landscape`: The width is greater than the height.
## Dark and Light Mode
You can use the `prefers-color-scheme` media feature to apply styles based on the user's system preference for dark or light mode.
```css
@media (prefers-color-scheme: dark) {
  body {
    background-color: black;
    color: white;
  }
}
@media (prefers-color-scheme: light) {
  body {
    background-color: white;
    color: black;
  }
}
```
- `prefers-color-scheme: dark`: Applies styles when the user prefers a dark color scheme.
- `prefers-color-scheme: light`: Applies styles when the user prefers a light color scheme.
## High Contrast Mode   
You can use the `prefers-contrast` media feature to apply styles based on the user's preference for high contrast mode.
```css
@media (prefers-contrast: more) {
  body {
    background-color: black;
    color: yellow;
  }
}   
@media (prefers-contrast: less) {
  body {
    background-color: white;
    color: gray;
  }
}
```
- `prefers-contrast: more`: Applies styles when the user prefers higher contrast.
- `prefers-contrast: less`: Applies styles when the user prefers lower contrast.    
- `prefers-contrast: no-preference`: Applies styles when the user has no specific contrast preference.
## Resolution
You can use the `resolution` media feature to apply styles based on the screen resolution of the device.
```css
@media (min-resolution: 2dppx) {
  /* Styles for high-resolution screens (e.g., Retina displays) */
}   
@media (max-resolution: 1dppx) {
  /* Styles for standard-resolution screens */
}
```
- `min-resolution`: Applies styles for screens with a minimum resolution (e.g., 2dppx for Retina displays).
- `max-resolution`: Applies styles for screens with a maximum resolution (e.g., 1dppx for standard displays).
- `dppx`: Dots per pixel (1dppx = 96dpi).
- `dpi`: Dots per inch (e.g., 192dpi for high-resolution screens).
## Aspect Ratio
You can use the `aspect-ratio` media feature to apply styles based on the aspect ratio of the viewport.
```css
@media (aspect-ratio: 16/9) {
  /* Styles for 16:9 aspect ratio */
}
@media (aspect-ratio: 4/3) {
  /* Styles for 4:3 aspect ratio */
}
```
- `aspect-ratio`: The ratio of the width to the height of the viewport.     
- You can also use `min-aspect-ratio` and `max-aspect-ratio` to apply styles based on minimum and maximum aspect ratios.
## Pointer and Hover
You can use the `pointer` and `hover` media features to apply styles based on the user's input device capabilities.
```css  
@media (pointer: fine) {
  /* Styles for devices with a fine pointer (e.g., mouse) */
}
@media (pointer: coarse) {
  /* Styles for devices with a coarse pointer (e.g., touchscreens) */
}
@media (hover: hover) {
  /* Styles for devices that support hover (e.g., mouse) */
}
@media (hover: none) {
  /* Styles for devices that do not support hover (e.g., touchscreens) */
}
```
- `pointer: fine`: Applies styles for devices with a precise pointing device (like a mouse).
- `pointer: coarse`: Applies styles for devices with a less precise pointing device (like a touchscreen).
- `hover: hover`: Applies styles for devices that support hover interactions (like a mouse).
- `hover: none`: Applies styles for devices that do not support hover interactions (like a touchscreen).    
- Use `pointer` and `hover` to enhance user experience based on the input method.
## When to actually use media queries
- Use media queries to create responsive designs that adapt to different screen sizes and orientations.
- Use media queries to optimize the layout and appearance of web pages for various devices, including desktops, tablets, and smartphones.
- Use media queries to implement a mobile-first design approach, starting with styles for small screens and adding styles for larger screens as needed.
- Use media queries to enhance accessibility by adapting styles based on user preferences, such as dark mode or high contrast mode.
- Use media queries to improve performance by loading only the necessary styles for the device being used.
- Use media queries to create print-friendly versions of web pages by applying specific styles for printing.
- Use media queries to test and debug responsive designs in different browsers and devices.
- Use media queries to manage complex layouts and ensure that content is displayed correctly across a wide range of devices.

## Additional Resources
- [MDN Web Docs - Using Media Queries](https://developer.mozilla.org/en-US/docs/Web/CSS/Media_Queries/Using_media_queries)
- [CSS-Tricks - A Complete Guide to CSS Media Queries](https://css-tricks.com/a-complete-guide-to-css-media-queries/)
- [W3Schools - CSS Media Queries](https://www.w3schools.com/css/css_rwd_mediaqueries.asp)
- [Can I use...](https://caniuse.com/) - Check browser support for CSS features.

# Advanced CSS: Transforms, Animations, Filters
This section covers advanced CSS techniques including transforms, animations, and filters to enhance the visual presentation of web pages.
## Transforms
CSS transforms allow you to modify the coordinate space of the CSS visual formatting model. You can translate, rotate, scale, and skew elements.
**Common Transform Functions:**
- `translate(x, y)`: Moves an element from its current position by x (horizontal) and y (vertical) values.
- `rotate(angle)`: Rotates an element clockwise by the specified angle (in degrees).
- `scale(x, y)`: Scales an element by x (horizontal) and y (vertical) factors.
- `skew(x, y)`: Skews an element along the x and y axes by the specified angles.
**Transform Example:**
```css
.box {
  transform: translate(50px, 100px) rotate(45deg) scale(1.5);
}
```
- This will move the element 50px to the right and 100px down, rotate it 45 degrees, and scale it to 1.5 times its original size.
**Transform Origin:**
- The `transform-origin` property sets the point around which a transformation is applied.
- Default is `50% 50%` (center of the element).
```css
.box {
    transform-origin: top left;
    }
    ``` 
- This sets the origin to the top-left corner of the element.
**Centering a div with transform:**
```css
.box {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
}
```
- This centers the `.box` element both vertically and horizontally within its containing element.
- The `translate(-50%, -50%)` moves the element back by half of its own width and height, effectively centering it.
- Ensure the parent element has `position: relative;` or another positioning context for absolute positioning to work correctly.
**3D Transforms:**
- `perspective(n)`: Defines the perspective from which a 3D element is viewed.
- `rotateX(angle)`, `rotateY(angle)`, `rotateZ(angle)`: Rotates an element around the X, Y, or Z axis.
- `translateZ(n)`: Moves an element along the Z-axis.
**3D Transform Example:**
```css
.box {
  perspective: 500px;
  transform: rotateY(45deg);
}
```
- This will give a 3D effect by rotating the element around the Y-axis with a perspective of 500px.
- Make sure to apply `transform-style: preserve-3d;` to parent elements if you want to maintain 3D transformations for child elements.
- Use `backface-visibility: hidden;` to hide the back side of an element when it is rotated.

**Using 3D transform to make a parallax effect:**
```css
.container {
  perspective: 1000px;
}
.layer {
  transform-style: preserve-3d;
}
.layer1 {
  transform: translateZ(-100px) scale(0.8);
}
.layer2 {
  transform: translateZ(-50px) scale(0.9);
}
.layer3 {
  transform: translateZ(0) scale(1);
}
```
- This creates a parallax effect where layers move at different speeds based on their Z position.
- The `.container` sets the perspective for the 3D effect.  
- Each `.layer` is transformed in 3D space, with layers further back appearing smaller and moving slower than those closer to the viewer.
## Animations
CSS animations allow you to animate transitions between CSS styles.
To create an animation, you define keyframes and then apply the animation to an element. You can control the duration, timing function, delay, iteration count, direction, and fill mode of the animation.
Use the `@keyframes` rule to define the animation. You should not use animation extensively for performance and accessibility reasons.
**Keyframes Example:**
```css
@keyframes slide {
  0% {
    transform: translateX(0);
  }
  100% {
    transform: translateX(100px);
  }
}
``` 
- This defines an animation named `slide` that moves an element from its original position to 100px to the right.
- Apply the animation to an element:
```css.box {
  animation: slide 2s ease-in-out infinite;
}
```
- This applies the `slide` animation to the `.box` element, making it last 2 seconds, use an ease-in-out timing function, and repeat infinitely.
**Animation Properties:**
- `animation-name`: Name of the keyframes to use.
- `animation-duration`: Duration of the animation (e.g., `2s`, `500ms`).
- `animation-timing-function`: Speed curve of the animation (e.g., `linear`, `ease`, `ease-in`, `ease-out`, `ease-in-out`).
- `animation-delay`: Delay before the animation starts (e.g., `1s`, `500ms`).
- `animation-iteration-count`: Number of times the animation should repeat (e.g., `infinite`, `1`, `3`).
- `animation-direction`: Direction of the animation (e.g., `normal`, `reverse`, `alternate`, `alternate-reverse`).
- `animation-fill-mode`: Defines how a CSS animation applies styles to its target before and after its execution (e.g., `forwards`, `backwards`, `both`, `none`).
- `animation` (shorthand): Combines all the above properties into one line. This the order is important: `animation: name duration timing-function delay iteration-count direction fill-mode;`
**Pause and Resume Animation:**
```css
.box {
  animation-play-state: paused; /* Pauses the animation */
}
.box:hover {
  animation-play-state: running; /* Resumes the animation on hover */
}
```
- This pauses the animation by default and resumes it when the element is hovered over.
## Filters
CSS filters allow you to apply visual effects to elements, such as blurring, brightness adjustment, contrast adjustment, and more.
**Common Filter Functions:**
- `blur(px)`: Applies a Gaussian blur to the element. The value is the radius of the blur in pixels.
- `brightness(%)`: Adjusts the brightness of the element. Values over 100% make it brighter, values under 100% make it darker.
- `contrast(%)`: Adjusts the contrast of the element. Values over 100% increase contrast, values under 100% decrease it.
- `grayscale(%)`: Converts the element to grayscale. 100% is fully grayscale, 0% is the original color.
- `sepia(%)`: Applies a sepia tone to the element. 100% is fully sepia, 0% is the original color.
- `invert(%)`: Inverts the colors of the element. 100% is fully inverted, 0% is the original color.
- `saturate(%)`: Adjusts the saturation of the element. Values over 100% increase saturation, values under 100% decrease it.
- `hue-rotate(deg)`: Rotates the hue of the element by the specified degrees.
**Filter Example:**
```css
.image {
  filter: blur(5px) brightness(150%) contrast(120%);
}
```
- This applies a 5px blur, increases brightness by 150%, and increases contrast by 120% to the `.image` element.
**Multiple Filters:**
```css
.image {
  filter: blur(5px) brightness(150%) contrast(120%);
}
``` 
- You can chain multiple filter functions together by separating them with spaces.
- Each filter function is applied in the order they are listed.
- Note that excessive use of filters can impact performance, especially on large images or complex elements.
**Hover Effect with Filter:**
```css
.image {
  transition: filter 0.3s ease;
}
.image:hover {
  filter: grayscale(100%);
}
```
- This applies a grayscale filter to the `.image` element when it is hovered over, with a smooth transition effect lasting 0.3 seconds.
- The `transition` property is used to animate the change in the filter property when hovering.
- You can adjust the transition duration and timing function as needed.
**Note:** CSS filters can be applied to any HTML element, not just images. However, they may have different visual effects depending on the content of the element.
**Performance Consideration:**
- Applying filters can be performance-intensive, especially on large images or complex elements. Use them judiciously to avoid slowing down page rendering.
- Test performance on different devices and browsers to ensure a smooth user experience.
- Consider using `will-change: filter;` on elements that will have filters applied to optimize rendering.
- This hints to the browser that the filter property will change, allowing it to optimize rendering in advance.
```css
.image {
  will-change: filter;
}
```
- Use hardware acceleration (e.g., `transform: translateZ(0);`) to improve performance when applying filters.
```css
.image {
  transform: translateZ(0);
}
```
- This creates a new layer for the element, which can help with performance when applying filters or animations.
- Be cautious with excessive use of filters, as they can lead to increased memory usage and slower performance, especially on mobile devices.
- Always test the performance impact of filters on your specific use case.

**Glass effect using backdrop-filter:**
```css
.glass {
  background: rgba(255, 255, 255, 0.2);
  backdrop-filter: blur(10px);
  -webkit-backdrop-filter: blur(10px); /* For Safari */
  border: 1px solid rgba(255, 255, 255, 0.3);
}
```
- This creates a glass-like effect by applying a blur to the background behind the `.glass` element.
- The `backdrop-filter` property applies the filter to the area behind the element, creating a frosted glass effect.
- The `background` property uses a semi-transparent white color to enhance the glass effect.    
- The `border` adds a subtle outline to the glass element.
- Note that `backdrop-filter` may not be supported in all browsers, so check compatibility before using it in production.

## Additional Resources
- [MDN Web Docs - CSS Transforms](https://developer.mozilla.org/en-US/docs/Web/CSS/transform)
- [MDN Web Docs - CSS Animations](https://developer.mozilla.org/en-US/docs/Web/CSS/animation)
- [MDN Web Docs - CSS Filters](https://developer.mozilla.org/en-US/docs/Web/CSS/filter)
- [CSS-Tricks - A Complete Guide to CSS Transforms](https://css-tricks.com/almanac/properties/t/transform/)
- [CSS-Tricks - A Complete Guide to CSS Animations](https://css-tricks.com/almanac/properties/a/animation/)
- [CSS-Tricks - A Complete Guide to CSS Filters](https://css-tricks.com/almanac/properties/f/filter/)
- [Can I use...](https://caniuse.com/) - Check browser support for CSS features.
- [CSS Animation Performance Tips](https://developers.google.com/web/fundamentals/performance/rendering/optimize-css-animation)
- [CSS Filter Effects Performance Tips](https://developers.google.com/web/updates/2016/06/css-filter-effects)


# CSS Units

CSS units are used to specify lengths, sizes, spacing, and other measurements. The most useful split is between fixed units and units that depend on context such as font size, parent size, or viewport size.

## Absolute Units

Absolute units have a fixed relationship to physical units. In screen CSS, `px` is the unit you will see most often.

- `px` (CSS pixels)
- `pt` (points)
- `pc` (picas)
- `cm` (centimeters)
- `mm` (millimeters)
- `Q` (quarter-millimeters)
- `in` (inches)

## Relative Units

Relative units are based on another measurement and are usually better for responsive, accessible layouts.

- `em` (relative to the font size of the element)
- `rem` (relative to the font size of the root element)
- `%` (percentage of the parent or containing context)
- `ch` (width of the `0` character in the current font)
- `ex` (height of the `x` character in the current font)
- `lh` (line height of the element)
- `rlh` (line height of the root element)
- `fr` (fraction of available space in CSS Grid)

## Viewport Units

Viewport units are based on the browser viewport.

- `vw` and `vh` (viewport width and height)
- `vmin` and `vmax` (smaller or larger viewport dimension)
- `vi` and `vb` (viewport inline and block size)
- `dvw`, `dvh`, `dvi`, `dvb` (dynamic viewport sizes)
- `svw`, `svh` (small viewport sizes)
- `lvw`, `lvh` (large viewport sizes)

Dynamic, small, and large viewport units are especially useful on mobile, where browser UI can change the visible viewport height.

## Choosing Units

- Use `rem` for most font sizes and consistent spacing systems.
- Use `%`, `fr`, `minmax()`, and `auto` for flexible layouts.
- Use `px` for small fixed details such as borders.
- Use viewport units when an element should intentionally relate to the screen size.
- Avoid locking large layout areas to fixed widths and heights unless the format requires it.

## Example

```css
.container {
  width: min(80vw, 64rem);
  padding: 1rem;
}

.text {
  font-size: 1.125rem;
  line-height: 1.6;
  max-width: 65ch;
}

.grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(12rem, 1fr));
  gap: 1rem;
}
```

## Additional Resources

- [MDN Web Docs on CSS Units](https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks/Values_and_units)
- [CSS-Tricks on CSS Units](https://css-tricks.com/the-lengths-of-css/)
- [W3Schools CSS Units](https://www.w3schools.com/cssref/css_units.php)

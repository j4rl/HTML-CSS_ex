# Text, Media & Lists

## Text Content: Tags & Structure

### Headings & Paragraphs

- Use `<h1>`-`<h6>` for headings; they should form a logical hierarchy. A document typically has one `<h1>`.  
- Use `<p>` for paragraphs of text. Avoid inserting extra spacing by misusing `<br>`; use CSS margins instead.  

### Emphasis, Strong & Other Inline Tags

- `<strong>`: for strong importance (often rendered bold)  
- `<em>`: for emphasis (often rendered italic)  
- `<mark>`: highlights parts of text  
- `<small>`: for side notes or fine print  
- `<code>`: inline code snippets  

---

## Media: Images, Alt Text & Embedding

### Using Images Properly

- Use `<img src="…" alt="…" />` for images. The **`alt` attribute must be meaningful** or empty (`alt=""`) if the image is purely decorative. It helps users with screen-readers.  
- Don’t start `alt` text with “Image of…” or “Picture of…”; screen readers already know it’s an image.   
- Use `<figure>` + `<figcaption>` to group an image with its caption. This improves readability and semantic clarity.  

### Responsive & Accessible Media

- Provide width and height attributes or use CSS to avoid layout shift.  
- Consider responsive images using `<img srcset>` / `<picture>` when appropriate (this module covers basics; more advanced later).  
- For video/audio: include captions or transcripts, use native HTML5 elements (`<video>`, `<audio>`), provide controls.  

---

## Lists: Ordered, Unordered & Definition Lists

- **Unordered lists** (`<ul>`): when the order of items does *not* matter.  
- **Ordered lists** (`<ol>`): when order *does* matter.  
- **Definition lists** (`<dl>`, `<dt>`, `<dd>`): for terms + definitions or name/value pairs.  

### Lists Best Practices

- Nest lists only when needed; avoid deeply nested lists if possible (for readability).  
- Ensure list items are semantically appropriate—don’t pick list just for visual indentation.  

---

## Code Examples

### Example: Text with Inline Formatting

```html
<h1>Welcome to My Page</h1>
<p>This is a <strong>strong</strong> statement and this is <em>emphasised</em> text. Maybe we <mark>highlight</mark> something or show <code>inlineCode()</code>.</p>
```

### Example: Image with caption 
```html
<figure>
  <img src="mountain.jpg" alt="Snowy mountain peak under a clear blue sky">
  <figcaption>A view of Mount Rainier taken at sunrise.</figcaption>
</figure>
```

### Example: Lists
```html
<ul>
  <li>Apples</li>
  <li>Bananas</li>
  <li>Cherries</li>
</ul>

<ol>
  <li>Preheat oven to 200°C</li>
  <li>Mix ingredients</li>
  <li>Bake for 20 minutes</li>
</ol>

<dl>
  <dt>HTML</dt>
  <dd>HyperText Markup Language</dd>
  <dt>CSS</dt>
  <dd>Cascading Style Sheets</dd>
</dl>
```

## Best Practices & Accessibility Tips

- Always include alt text for images that convey information — skip or use empty alt (`alt=""`) for purely decorative images. 
- Use meaningful link text; avoid “click here” if possible.
- Use captions (via `<figcaption>`) when images need explanations.
- Ensure that text is readable: choose good font sizes, contrast, line-height, etc. (Most of this is CSS side, but relevant to how media and text show up together.)
- Use title and role attributes sparingly; only where they add necessary context not possible via semantic tags.

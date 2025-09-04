# Module 01 — HTML Structure

---

## 1. What You’ll Learn

- How semantic HTML establishes **meaning**, not just appearance.
- Why semantic elements like `<header>`, `<nav>`, `<main>`, `<section>`, `<article>`, and `<footer>` are essential.
- How using proper structure improves **accessibility**, **SEO**, and **maintainability**.

---

## 2. Why It Matters

- **Accessibility**: Semantic elements help assistive tools like screen readers understand page structure.  
- **SEO**: Search engines better index pages when markup includes meaningful tags. 
- **Readable Code**: Developers can quickly sense the intent behind each block. 

Semantic HTML is no longer optional—it’s the foundation for modern, inclusive web development. 

---

## 3. Essential Semantic Elements

| Element       | Purpose                                           |
|---------------|--------------------------------------------------|
| `<header>`    | Wraps intro content, logo, site-wide navigation  |
| `<nav>`       | Contains links for page or site navigation       |
| `<main>`      | Encapsulates the unique main content of the page |
| `<section>`   | Groups thematically related content              |
| `<article>`   | Holds a self-contained piece, e.g. a blog post   |
| `<aside>`     | Side notes, pull-quotes, or supplementary info   |
| `<footer>`    | Bottom area, such as copyright or contact links  | 

---

## 4. Common Pitfalls to Avoid

- **Don’t use `<div>` or `<span>`** where a semantic tag fits. Reserve these for layout or style only.   
- **Avoid skipping heading levels** (e.g., `<h1>` → `<h3>`). Proper nesting supports both SEO and accessibility.  
- Use `<table>` only for true tabular data—not layout.  
- Always include `<meta charset="utf-8">` and responsive viewport meta tags in `<head>`.

---

## 5. Example: Minimal Semantic Page

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="utf-8">
  <meta name="viewport" content="width=device-width, initial-scale=1">
  <title>My Semantic Page</title>
</head>
<body>
  <header>
    <h1>Welcome</h1>
    <nav>
      <ul>
        <li><a href="#home">Home</a></li>
      </ul>
    </nav>
  </header>
  <main>
    <article>
      <h2>Article Title</h2>
      <p>Article content here.</p>
    </article>
    <section>
      <h2>Section Heading</h2>
      <p>Section content here.</p>
    </section>
  </main>
  <footer>
    <p>&copy; 2025 My Website</p>
  </footer>
</body>
</html>
```

---

6. Specific HTML tags to know

| Tag           | Description                                      |
|---------------|--------------------------------------------------|
| `<a>`         | Defines a hyperlink                              |
| `<img>`       | Embeds an image                                  |
| `<p>`         | Represents a paragraph                           |
| `<ul>`, `<ol>`| Unordered and ordered lists                      |
| `<li>`        | List item                                        |
| `<h1>`-`<h6>` | Headings, with `<h1>` as the highest level       |
| `<div>`       | Generic container for flow content               |  
| `<span>`      | Generic inline container                         |
| `<strong>`    | Indicates strong importance (typically bold)     |
| `<em>`        | Indicates emphasis (typically italic)            |
| `<br>`        | Line break                                       |
| `<hr>`        | Thematic break (horizontal rule)                 |
| `<meta>`      | Metadata about the HTML document                 |
| `<link>`      | Links to external resources (e.g., CSS files)    |
| `<script>`    | Embeds or references executable code (e.g., JS)  |
| `<style>`     | Embeds CSS styles                                |
| `<form>`      | Represents a form for user input                 |
| `<input>`     | Input control within a form                      |
| `<button>`    | Clickable button                                 |
| `<label>`     | Label for an `<input>` element                   |
| `<fieldset>`  | Groups related elements in a form                |
| `<legend>`    | Caption for a `<fieldset>`                       |
| `<figure>`    | Self-contained content, like images with captions|
| `<figcaption>`| Caption for a `<figure>`                         |
| `<audio>`     | Embeds sound content                             |
| `<video>`     | Embeds video content                             |
| `<source>`    | Specifies multiple media resources               |
|               | for `<audio>` or `<video>`                       |
| `<iframe>`    | Embeds another HTML page within the current page |
| `<code>`      | Represents a fragment of computer code           |
| `<pre>`       | Represents preformatted text                     |
| `<blockquote>`| Represents a section quoted from another source  |
| `<cite>`      | Represents the title of a work                   |
| `<abbr>`      | Represents an abbreviation or acronym            |
| `<time>`      | Represents a specific time or date               |

## 6.1 Usage Tips for Common Tags as a, img, figure, figcaption and iframe
- Always use the `alt` attribute with `<img>` to provide descriptive text for screen readers and when images fail to load.
- Wrap images and their captions in `<figure>` and use `<figcaption>` for the caption to enhance semantic meaning.
- Use `<a>` for all hyperlinks, ensuring the `href` attribute points to a valid URL. Avoid using `<a>` without `href`.
- When embedding external content with `<iframe>`, always include a descriptive `title` attribute to improve accessibility. 
- Ensure that `<iframe>` content is from a trusted source to avoid security risks.
- Use `<a>` with meaningful link text that describes the destination or action, rather than generic text like "click here."
- For complex images, consider using `<figure>` to group the image and its caption, enhancing both semantics and accessibility.


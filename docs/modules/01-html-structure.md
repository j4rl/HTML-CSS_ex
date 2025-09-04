# Module 01 — HTML Structure

**Goal:** Learn to use semantic HTML to define structure and meaning.

- HTML defines *content structure and meaning*; CSS handles presentation. HTML (HyperText Markup Language) 
establishes how your document is organized.
- Use appropriate semantic elements (`<header>`, `<nav>`, `<main>`, `<article>`, `<section>`, `<footer>`), 
not generic `<div>`s. This improves **accessibility**, **SEO**, and maintainability.
- Example of minimal semantic page:
  ```html
  <!doctype html>
  <html lang="en">
  <head>
    <meta charset="utf-8" />
    <meta name="viewport" content="width=device-width,initial-scale=1" />
    <title>My Page</title>
  </head>
  <body>
    <header><h1>Site Title</h1></header>
    <nav aria-label="Primary">…</nav>
    <main>…</main>
    <footer>…</footer>
  </body>
  </html>
```

- Use `<h1>`-`<h6>` for headings, `<p>` for paragraphs, `<a>` for links, `<ul>`/`<ol>` for lists, and `<img>` for images with `alt` text.
  - Headings should be nested properly (e.g., `<h2>` under `<h1>`, etc.) to reflect document structure.
  - Usage of `<div>` and `<span>` should be limited to cases where no semantic element fits.
  - `<br>` should be used for line breaks only in text, not for spacing.
  - `<hr>` can be used to separate content or indicate a thematic change.
  - This is how you use the image tag: `<img src="image.jpg" alt="Description of image">`
  - Use `<a href="url">link text</a>` for hyperlinks. For links that open in a new tab, add `target="_blank"` and `rel="noopener noreferrer"` for security.
- Tables should use `<table>`, `<thead>`, `<tbody>`, `<tr>`, `<th>`, and `<td>` for tabular data, not for layout.
    - Example of a table:
    ```html
    <table>
        <thead>
        <tr><th>Header 1</th><th>Header 2</th></tr>
        </thead>
        <tbody>
        <tr><td>Data 1</td><td>Data 2</td></tr>
        <tr><td>Data 3</td><td>Data 4</td></tr>
        </tbody>
    </table>
    ```
- Always include `<meta charset="utf-8">` and `<meta name="viewport" content="width=device-width, initial-scale=1">` in `<head>` for proper character encoding and responsive design.
- Use comments (`<!-- comment -->`) to explain sections of your HTML for future reference.
- Validate your HTML with tools like the [W3C Markup Validation Service](https://validator.w3.org/) to ensure correctness.

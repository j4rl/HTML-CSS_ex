
# Module 02 — Text & Media

**Goal:** Understand how to structure text and media with semantic tags.

- HTML provides elements like `<p>`, `<ul>`, `<strong>`, `<em>`, `<img>`, `<figure>`, `<figcaption>`—each communicating meaning. 
- Use `<img>` with `alt`, `<figure>` to wrap images + captions, `<figcaption>` for captions. This improves **accessibility** and content clarity.

**Next:** [Exercise 02 — Card Layout](../exercises/02-card-layout/TASK.md)

# 1. Key Text Elements
- `<p>`: Paragraphs of text.
- `<h1>` to `<h6>`: Headings, with `<h1>` as the highest level.
- `<ul>`, `<ol>`, `<li>`: Unordered and ordered lists.
- `<strong>`, `<em>`: Important text (bold) and emphasized text (italic).
- `<blockquote>`: Quoted text.  
- `<a>`: Hyperlinks to other pages or resources.
- `<br>`: Line break.
- `<hr>`: Thematic break (horizontal rule).
# 2. Key Media Elements
- `<img>`: Embeds images. Always include `alt` text for accessibility.
- `<figure>`: Wraps media content like images, diagrams, or code snippets.
- `<figcaption>`: Provides a caption for the content in `<figure>`. 
- `<audio>`: Embeds sound content.
- `<video>`: Embeds video content.
- `<source>`: Specifies multiple media resources for `<audio>` or `<video>`.
- `<iframe>`: Embeds another HTML page within the current page. 
# 3. Example Usage

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Text and Media Example</title>
</head>
<body>
    <h1>Welcome to My Page</h1>
    <p>This is a sample paragraph demonstrating text elements in HTML.</p>
    
    <h2>List of Items</h2>
    <ul>
        <li>First item</li>
        <li>Second item with <strong>important text</strong></li>
        <li>Third item with <em>emphasized text</em></li>
    </ul>
    
    <h2>Image Example</h2>
    <figure>
        <img src="example.jpg" alt="A descriptive text about the image">
        <figcaption>This is an example image with a caption.</figcaption>
    </figure>
    
    <h2>Video Example</h2>
    <video controls>
        <source src="example.mp4" type="video/mp4">
        Your browser does not support the video tag.
    </video>
</body>
</html>
```
---

[← Module 01 — HTML Structure](01-html-structure.md) · [Module 03 — Forms →](03-forms.md)

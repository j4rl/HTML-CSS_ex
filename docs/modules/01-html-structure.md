# Module 01 — HTML Structure

---

## 1. What You’ll Learn

- How semantic HTML establishes **meaning**, not just appearance.
- Why semantic elements like `<header>`, `<nav>`, `<main>`, `<section>`, `<article>`, and `<footer>` are essential.
- How using proper structure improves **accessibility**, **SEO**, and **maintainability**. :contentReference[oaicite:1]{index=1}

---

## 2. Why It Matters

- **Accessibility**: Semantic elements help assistive tools like screen readers understand page structure. :contentReference[oaicite:2]{index=2}  
- **SEO**: Search engines better index pages when markup includes meaningful tags. :contentReference[oaicite:3]{index=3}  
- **Readable Code**: Developers can quickly sense the intent behind each block. :contentReference[oaicite:4]{index=4}

Semantic HTML is no longer optional—it’s the foundation for modern, inclusive web development. :contentReference[oaicite:5]{index=5}

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
| `<footer>`    | Bottom area, such as copyright or contact links  | :contentReference[oaicite:6]{index=6}

---

## 4. Common Pitfalls to Avoid

- **Don’t use `<div>` or `<span>`** where a semantic tag fits. Reserve these for layout or style only. :contentReference[oaicite:7]{index=7}  
- **Avoid skipping heading levels** (e.g., `<h1>` → `<h3>`). Proper nesting supports both SEO and accessibility. :contentReference[oaicite:8]{index=8}  
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

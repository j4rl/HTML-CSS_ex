# HTML Basics

## What is HTML

- HTML (HyperText Markup Language) is the standard language for creating web pages. It provides the *structure* of a page.   
- An HTML document is made of nested elements (tags), attributes, and content.   
- The `<!DOCTYPE html>` declaration at the top informs the browser to render using HTML5 standard. 

## Essential Document Structure

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="utf-8">
  <meta name="viewport" content="width=device-width, initial-scale=1">
  <title>Page Title</title>
</head>
<body>
  <!-- visible content goes here -->
</body>
</html>
```

| Tag           | Purpose                                                        |
| ------------- | -------------------------------------------------------------- |
| `<html>`      | Root of the HTML document.                                     |
| `<head>`      | Meta-information (title, links, scripts) that is not visible.  |
| `<title>`     | Title shown in browser tab.                                    |
| `<body>`      | Visible content of the page.                                   |
| `<h1>`-`<h6>` | Headings, forming a hierarchy.                                 |
| `<p>`         | Paragraph (text block).                                        |

## Best Practices
- Always use lang="en" (or whatever language the content is) on <html>.
- Use lowercase tags. Consistency helps.
- Close all tags properly. Proper nesting matters.
- Comments: `<!-- comment -->` to explain complex sections.
- Validate HTML (e.g. W3C validator) to catch mistakes.

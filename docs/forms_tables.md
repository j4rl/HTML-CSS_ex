# Forms and Tables

## Forms in HTML

Forms are used to collect user input. The `<form>` element wraps input controls and defines how data is sent.

**Basic Structure:**

```html
<form action="submit_url" method="post">
  <label for="username">Username:</label>
  <input type="text" id="username" name="username">
  <label for="email">Email:</label>
  <input type="email" id="email" name="email">

  <input type="submit" value="Submit">
</form>
```

- `action`: URL where form data is sent.
- `method`: HTTP method (`get` or `post`). `get` appends data to the URL; `post` sends it in the request body.
- `<label>`: Associates text with a form control for better accessibility.
- `<input>`: Various types of input fields. (See below)

**Common Input Types:**

- `<input type="text">` – single-line text
- `<input type="password">` – password field
- `<input type="email">` – email address
- `<input type="checkbox">` – checkbox
- `<input type="radio">` – radio button
- `<input type="submit">` – submit button
- `<textarea>` – multi-line text
- `<select>` – dropdown list

**Attributes:**

- `name`: Name of the input, used as key when data is submitted.
- `id`: Unique identifier, used with `<label>`.
- `placeholder`: Placeholder text inside input.
- `required`: Makes the field mandatory.
- `disabled`: Disables the input field.
- `readonly`: Makes the input read-only.
- `value`: Default value of the input.
- `maxlength`: Maximum number of characters allowed.
- `minlength`: Minimum number of characters allowed.
- `min` and `max`: Minimum and maximum values for numeric inputs.
- `step`: Increment step for numeric inputs.
- `pattern`: Regex pattern for validation.

**Regex Example:**

```html
<input type="text" pattern="[A-Za-z]{3,}" title="Three or more letters">
```

**Validation:**

- HTML5 provides built-in validation for types like `email`, `url`, `number`, etc.
- Custom validation can be done using the `pattern` attribute.
- The `novalidate` attribute on the `<form>` element can disable built-in validation.

---

## Tables in HTML

Tables display tabular data using rows and columns.

**Basic Structure:**

```html
<table>
  <caption>Sample Table</caption>
  <thead>
    <tr>
      <th scope="col">Month</th>
      <th scope="col">Revenue</th>
      <th scope="col">Change</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>January</td>
      <td>$10,000</td>
      <td>+5%</td>
    </tr>
    <tr>
      <td>February</td>
      <td>$12,000</td>
      <td>+20%</td>
    </tr>
  </tbody>
</table>
```

- `<table>`: Table container
- `<caption>`: Table title (optional)
- `<thead>`, `<tbody>`, `<tfoot>`: Table sections
- `<tr>`: Table row
- `<th>`: Header cell
- `<td>`: Data cell

**Attributes:**

- `colspan` and `rowspan` for merging cells

```html
<th colspan="2">Merged Header</th>
<td rowspan="2">Merged Cell</td>
```

**Accessibility:**

- Use `<caption>` for table title.
- Use `<th>` for headers and scope attribute (`scope="col"` or `scope="row"`) for better screen reader support.
- Use `<thead>`, `<tbody>`, and `<tfoot>` to structure the table for better readability and accessibility.
- Use `<details>` and `<summary>` for collapsible explanatory sections when needed.
- Avoid adding ARIA roles to normal data tables. Use native table elements first, then add ARIA only for complex custom widgets.
- Use CSS for styling tables (borders, spacing, colors).

---

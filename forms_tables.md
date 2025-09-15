# Forms & Tables Reference

## HTML Forms (Without JavaScript)

### Basic Form Structure

Forms are used to collect user input and submit it to a server. The basic structure uses the `<form>` element as a container for form controls.

```html
<form action="/submit" method="post">
  <!-- form controls go here -->
  <input type="submit" value="Submit">
</form>
```

| Attribute | Purpose | Values |
| --------- | ------- | ------ |
| `action` | URL where form data is sent | URL or relative path |
| `method` | HTTP method for submission | `get` (default), `post` |
| `enctype` | How form data is encoded | `application/x-www-form-urlencoded` (default), `multipart/form-data` |
| `autocomplete` | Browser autocomplete behavior | `on` (default), `off` |
| `novalidate` | Disable HTML5 validation | Boolean attribute |

---

## Form Input Elements

### Text Input Types

```html
<!-- Basic text input -->
<label for="username">Username:</label>
<input type="text" id="username" name="username" required>

<!-- Email input with validation -->
<label for="email">Email:</label>
<input type="email" id="email" name="email" required>

<!-- Password input -->
<label for="password">Password:</label>
<input type="password" id="password" name="password" minlength="8" required>

<!-- Multi-line text -->
<label for="message">Message:</label>
<textarea id="message" name="message" rows="4" cols="50" placeholder="Enter your message"></textarea>
```

### Specialized Input Types

```html
<!-- Number input with constraints -->
<label for="age">Age:</label>
<input type="number" id="age" name="age" min="18" max="120" step="1">

<!-- Date and time inputs -->
<label for="birthdate">Birth Date:</label>
<input type="date" id="birthdate" name="birthdate">

<label for="appointment">Appointment Time:</label>
<input type="datetime-local" id="appointment" name="appointment">

<!-- File upload -->
<label for="avatar">Profile Picture:</label>
<input type="file" id="avatar" name="avatar" accept="image/*">

<!-- Color picker -->
<label for="color">Favorite Color:</label>
<input type="color" id="color" name="color" value="#ff0000">

<!-- URL input -->
<label for="website">Website:</label>
<input type="url" id="website" name="website" placeholder="https://example.com">

<!-- Search input -->
<label for="search">Search:</label>
<input type="search" id="search" name="search" placeholder="Search...">
```

### Selection Controls

```html
<!-- Radio buttons (single selection) -->
<fieldset>
  <legend>Choose your size:</legend>
  <input type="radio" id="small" name="size" value="small">
  <label for="small">Small</label>
  
  <input type="radio" id="medium" name="size" value="medium" checked>
  <label for="medium">Medium</label>
  
  <input type="radio" id="large" name="size" value="large">
  <label for="large">Large</label>
</fieldset>

<!-- Checkboxes (multiple selection) -->
<fieldset>
  <legend>Select your interests:</legend>
  <input type="checkbox" id="sports" name="interests" value="sports">
  <label for="sports">Sports</label>
  
  <input type="checkbox" id="music" name="interests" value="music" checked>
  <label for="music">Music</label>
  
  <input type="checkbox" id="reading" name="interests" value="reading">
  <label for="reading">Reading</label>
</fieldset>

<!-- Dropdown select -->
<label for="country">Country:</label>
<select id="country" name="country" required>
  <option value="">-- Select a country --</option>
  <option value="us">United States</option>
  <option value="ca">Canada</option>
  <option value="uk">United Kingdom</option>
  <option value="de">Germany</option>
</select>

<!-- Multi-select dropdown -->
<label for="languages">Programming Languages:</label>
<select id="languages" name="languages" multiple size="4">
  <option value="javascript">JavaScript</option>
  <option value="python">Python</option>
  <option value="java">Java</option>
  <option value="cpp">C++</option>
  <option value="rust">Rust</option>
</select>
```

---

## Form Validation (HTML5)

### Built-in Validation Attributes

```html
<form action="/register" method="post">
  <!-- Required field -->
  <label for="username">Username (required):</label>
  <input type="text" id="username" name="username" required>
  
  <!-- Pattern validation -->
  <label for="phone">Phone (XXX-XXX-XXXX):</label>
  <input type="tel" id="phone" name="phone" pattern="[0-9]{3}-[0-9]{3}-[0-9]{4}" 
         title="Format: 123-456-7890">
  
  <!-- Length constraints -->
  <label for="bio">Bio (50-500 characters):</label>
  <textarea id="bio" name="bio" minlength="50" maxlength="500" required></textarea>
  
  <!-- Numeric constraints -->
  <label for="salary">Expected Salary ($30,000 - $200,000):</label>
  <input type="number" id="salary" name="salary" min="30000" max="200000" step="1000">
  
  <input type="submit" value="Register">
</form>
```

### Custom Validation Messages

```html
<!-- Using title attribute for custom messages -->
<input type="email" id="email" name="email" required 
       title="Please enter a valid email address">

<!-- Pattern with custom message -->
<input type="text" id="zipcode" name="zipcode" 
       pattern="[0-9]{5}(-[0-9]{4})?" 
       title="Please enter a valid ZIP code (12345 or 12345-6789)">
```

---

## Form Accessibility Best Practices

### Proper Labeling

```html
<!-- Method 1: Explicit association -->
<label for="email">Email Address:</label>
<input type="email" id="email" name="email" required>

<!-- Method 2: Implicit association -->
<label>
  Email Address:
  <input type="email" name="email" required>
</label>

<!-- For complex forms, use fieldset and legend -->
<fieldset>
  <legend>Shipping Address</legend>
  <label for="street">Street:</label>
  <input type="text" id="street" name="street" required>
  
  <label for="city">City:</label>
  <input type="text" id="city" name="city" required>
</fieldset>
```

### Error Handling and Help Text

```html
<label for="password">Password:</label>
<input type="password" id="password" name="password" 
       aria-describedby="password-help password-error" required>
<div id="password-help">Must be at least 8 characters long</div>
<div id="password-error" role="alert" style="color: red; display: none;">
  Password is required
</div>
```

---

## Complete Form Example

```html
<form action="/contact" method="post" enctype="multipart/form-data">
  <fieldset>
    <legend>Contact Information</legend>
    
    <label for="name">Full Name:</label>
    <input type="text" id="name" name="name" required autocomplete="name">
    
    <label for="email">Email:</label>
    <input type="email" id="email" name="email" required autocomplete="email">
    
    <label for="phone">Phone:</label>
    <input type="tel" id="phone" name="phone" autocomplete="tel">
  </fieldset>
  
  <fieldset>
    <legend>Message Details</legend>
    
    <label for="subject">Subject:</label>
    <select id="subject" name="subject" required>
      <option value="">-- Choose a topic --</option>
      <option value="general">General Inquiry</option>
      <option value="support">Technical Support</option>
      <option value="sales">Sales Question</option>
    </select>
    
    <label for="priority">Priority:</label>
    <input type="radio" id="low" name="priority" value="low" checked>
    <label for="low">Low</label>
    <input type="radio" id="high" name="priority" value="high">
    <label for="high">High</label>
    
    <label for="message">Message:</label>
    <textarea id="message" name="message" rows="5" cols="50" 
              placeholder="Please describe your inquiry..." required></textarea>
    
    <label for="attachment">Attachment:</label>
    <input type="file" id="attachment" name="attachment" 
           accept=".pdf,.doc,.docx,.txt">
  </fieldset>
  
  <fieldset>
    <legend>Preferences</legend>
    
    <input type="checkbox" id="newsletter" name="newsletter" value="yes">
    <label for="newsletter">Subscribe to newsletter</label>
    
    <input type="checkbox" id="terms" name="terms" value="agreed" required>
    <label for="terms">I agree to the <a href="/terms">terms and conditions</a></label>
  </fieldset>
  
  <button type="submit">Send Message</button>
  <button type="reset">Clear Form</button>
</form>
```

---

## HTML Tables

### Basic Table Structure

Tables are used to display structured data in rows and columns. Every table should have a clear purpose and proper semantic markup.

```html
<table>
  <caption>Monthly Sales Report</caption>
  <thead>
    <tr>
      <th>Month</th>
      <th>Sales</th>
      <th>Growth</th>
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

### Table Elements Reference

| Element | Purpose | Required |
| ------- | ------- | -------- |
| `<table>` | Container for table content | Yes |
| `<caption>` | Table title/description | Recommended |
| `<thead>` | Groups header content | Recommended |
| `<tbody>` | Groups body content | Recommended |
| `<tfoot>` | Groups footer content | Optional |
| `<tr>` | Table row | Yes |
| `<th>` | Header cell | For headers |
| `<td>` | Data cell | For data |
| `<colgroup>` | Groups columns for styling | Optional |
| `<col>` | Column definition | Optional |

---

## Table Accessibility Features

### Headers and Scope

```html
<table>
  <caption>Quarterly Financial Results</caption>
  <thead>
    <tr>
      <th scope="col">Quarter</th>
      <th scope="col">Revenue</th>
      <th scope="col">Expenses</th>
      <th scope="col">Profit</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th scope="row">Q1 2024</th>
      <td>$100,000</td>
      <td>$80,000</td>
      <td>$20,000</td>
    </tr>
    <tr>
      <th scope="row">Q2 2024</th>
      <td>$120,000</td>
      <td>$85,000</td>
      <td>$35,000</td>
    </tr>
  </tbody>
</table>
```

### Complex Headers with IDs

```html
<table>
  <caption>Student Grades by Subject and Semester</caption>
  <thead>
    <tr>
      <th id="student">Student</th>
      <th id="fall">Fall Semester</th>
      <th id="spring">Spring Semester</th>
    </tr>
    <tr>
      <th id="name">Name</th>
      <th id="math-fall">Math</th>
      <th id="science-fall">Science</th>
      <th id="math-spring">Math</th>
      <th id="science-spring">Science</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td headers="student name">Alice Johnson</td>
      <td headers="fall math-fall">A</td>
      <td headers="fall science-fall">B+</td>
      <td headers="spring math-spring">A-</td>
      <td headers="spring science-spring">A</td>
    </tr>
  </tbody>
</table>
```

---

## Advanced Table Features

### Spanning Cells

```html
<table>
  <caption>Project Team Structure</caption>
  <thead>
    <tr>
      <th>Department</th>
      <th>Team Lead</th>
      <th>Members</th>
      <th>Budget</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td rowspan="2">Engineering</td>
      <td>John Smith</td>
      <td>5</td>
      <td>$500,000</td>
    </tr>
    <tr>
      <td>Jane Doe</td>
      <td>3</td>
      <td>$300,000</td>
    </tr>
    <tr>
      <td colspan="3">Total Budget</td>
      <td>$800,000</td>
    </tr>
  </tbody>
</table>
```

### Column Groups for Styling

```html
<table>
  <caption>Sales Performance</caption>
  <colgroup>
    <col>
    <col span="2" class="highlight">
    <col>
  </colgroup>
  <thead>
    <tr>
      <th>Salesperson</th>
      <th>Q1</th>
      <th>Q2</th>
      <th>Total</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Alice</td>
      <td>$50,000</td>
      <td>$60,000</td>
      <td>$110,000</td>
    </tr>
    <tr>
      <td>Bob</td>
      <td>$45,000</td>
      <td>$55,000</td>
      <td>$100,000</td>
    </tr>
  </tbody>
  <tfoot>
    <tr>
      <th>Total</th>
      <td>$95,000</td>
      <td>$115,000</td>
      <td>$210,000</td>
    </tr>
  </tfoot>
</table>
```

---

## Responsive Table Strategies

### Scrollable Tables

```html
<div style="overflow-x: auto;">
  <table>
    <caption>Wide Data Table</caption>
    <thead>
      <tr>
        <th>Name</th>
        <th>Email</th>
        <th>Phone</th>
        <th>Address</th>
        <th>City</th>
        <th>State</th>
        <th>ZIP</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td>John Doe</td>
        <td>john@example.com</td>
        <td>555-0123</td>
        <td>123 Main St</td>
        <td>Anytown</td>
        <td>CA</td>
        <td>12345</td>
      </tr>
    </tbody>
  </table>
</div>
```

### Data Tables with Summary

```html
<table>
  <caption>
    Annual Budget Summary 
    <small>(All figures in thousands of dollars)</small>
  </caption>
  <thead>
    <tr>
      <th scope="col">Category</th>
      <th scope="col">Planned</th>
      <th scope="col">Actual</th>
      <th scope="col">Variance</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th scope="row">Marketing</th>
      <td>$100</td>
      <td>$95</td>
      <td class="positive">$5</td>
    </tr>
    <tr>
      <th scope="row">Operations</th>
      <td>$500</td>
      <td>$520</td>
      <td class="negative">-$20</td>
    </tr>
    <tr>
      <th scope="row">Research</th>
      <td>$200</td>
      <td>$180</td>
      <td class="positive">$20</td>
    </tr>
  </tbody>
  <tfoot>
    <tr>
      <th scope="row">Total</th>
      <td>$800</td>
      <td>$795</td>
      <td class="positive">$5</td>
    </tr>
  </tfoot>
</table>
```

---

## Best Practices & Accessibility Tips

### Forms Best Practices

- **Always use labels**: Every form control should have an associated label for accessibility.
- **Group related fields**: Use `<fieldset>` and `<legend>` to group related form controls.
- **Provide clear instructions**: Use placeholder text, help text, and validation messages.
- **Use appropriate input types**: HTML5 input types provide better user experience and validation.
- **Make forms keyboard accessible**: Ensure all controls can be reached and operated with keyboard only.
- **Test with screen readers**: Verify that forms are announced correctly by assistive technologies.

### Table Best Practices

- **Use tables for data only**: Don't use tables for layout; use CSS Grid or Flexbox instead.
- **Always include captions**: Use `<caption>` to describe the table's purpose and content.
- **Mark up headers properly**: Use `<th>` elements with appropriate `scope` attributes.
- **Keep tables simple**: Complex tables are harder to navigate; consider breaking them into smaller tables.
- **Provide alternative formats**: For complex data, consider offering CSV downloads or simplified views.
- **Test responsiveness**: Ensure tables work well on different screen sizes.

### Common Accessibility Attributes

| Attribute | Purpose | Usage |
| --------- | ------- | ----- |
| `aria-label` | Provides accessible name | When visible label is insufficient |
| `aria-describedby` | Links to descriptive text | For help text and error messages |
| `aria-required` | Indicates required fields | Alternative to `required` attribute |
| `role="alert"` | Announces dynamic content | For error messages and status updates |
| `aria-expanded` | Shows collapsed/expanded state | For collapsible sections |
| `aria-hidden` | Hides decorative content | For purely visual elements |

### Validation and Error Handling

- **Validate on both client and server**: HTML5 validation is just the first line of defense.
- **Provide clear error messages**: Tell users exactly what went wrong and how to fix it.
- **Show errors near the relevant fields**: Don't just show a summary at the top.
- **Use semantic markup for errors**: Use `role="alert"` for dynamic error messages.
- **Don't disable the submit button**: Let validation messages guide the user instead.
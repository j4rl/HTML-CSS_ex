# ARIA & Accessibility

ARIA (Accessible Rich Internet Applications) is a set of attributes that enhance the accessibility of web content, especially for users with disabilities. It helps make dynamic content and advanced user interface controls more accessible.  
## Why ARIA and Accessibility Matter
- Accessibility ensures that all users, including those with disabilities, can access and interact with web content.
- ARIA provides additional information to assistive technologies (like screen readers) about the roles, states, and properties of elements.
- Using ARIA correctly can improve the user experience for people with disabilities, making your website more inclusive.
## Common ARIA Roles
| Role               | Description                                           | Example Element                                  |
| ------------------ | ----------------------------------------------------- | ------------------------------------------------ |
| `button`           | Represents a clickable button.                        | `<button aria-label="Close">X</button>`          |
| `dialog`           | Represents a dialog box or modal.                     | `<div role="dialog" aria-modal="true">...</div>` |
| `alert`            | Represents an important message.                      | `<div role="alert">Error occurred!</div>`        |
| `navigation`       | Represents a navigation section.                      | `<nav role="navigation">...</nav>`               |
| `main`             | Represents the main content of a document.            | `<main role="main">...</main>`                   |
| `banner`           | Represents site-oriented content at the top of the page. | `<header role="banner">...</header>`             |
| `complementary`    | Represents a supporting section of the document.      | `<aside role="complementary">...</aside>`        |
| `form`             | Represents a form.                                    | `<form role="form">...</form>`                   |
| `textbox`          | Represents an input field for text.                   | `<input type="text" role="textbox">`               |
| `checkbox`         | Represents a checkbox.                                | `<input type="checkbox" role="checkbox">`          |
| `radio`            | Represents a radio button.                            | `<input type="radio" role="radio">`             |
| `tablist`          | Represents a list of tabs.                            | `<div role="tablist">...</div>`                     |
| `tab`              | Represents a single tab.                              | `<button role="tab">Tab 1</button>`            |
| `tabpanel`         | Represents the content associated with a tab.         | `<div role="tabpanel">...</div>`                |
## Common ARIA Attributes
| Attribute          | Description                                           | Example                                          |
| ------------------ | ----------------------------------------------------- | ------------------------------------------------ |   
| `aria-label`       | Provides an accessible name for an element.           | `<button aria-label="Close">X</button>`          |
| `aria-labelledby`  | Identifies the element that labels the current element. | `<div aria-labelledby="label-id">...</div>` |
| `aria-describedby` | Identifies the element that describes the current element. | `<div aria-describedby="desc-id">...</div>` |
| `aria-hidden`      | Indicates whether an element is visible or hidden to assistive technologies. | `<div aria-hidden="true">Hidden content</div>`    |
| `aria-expanded`    | Indicates whether a collapsible element is expanded or collapsed. | | `<button aria-expanded="false">Menu</button>`      |
| `aria-controls`    | Identifies the element that is controlled by the current element. | `<button aria-controls="menu-id">Toggle Menu</button>` |
| `aria-live`        | Indicates that an element will be updated and describes the types of updates. | `<div aria-live="polite">...</div>`              |
| `aria-modal`       | Indicates that an element is a modal dialog.          | `<div role="dialog" aria-modal="true">...</div>` |
| `aria-required`    | Indicates that user input is required on an element.   | | `<input type="text" aria-required="true">`          |
| `aria-checked`     | Indicates the current "checked" state of checkboxes, radio buttons, and other widgets. | `<input type="checkbox" aria-checked="true">`      |
| `aria-selected`    | Indicates the current "selected" state of an element. | `<option aria-selected="true">Option 1</option>`   |
## Examples of ARIA Usage
**Button with ARIA Label:**
```html
<button aria-label="Close">X</button>
```
- The `aria-label` provides a descriptive name for screen readers.
**Collapsible Menu:**
```html
<button aria-expanded="false" aria-controls="menu">Menu</button>
<div id="menu" role="menu" aria-hidden="true">
  <a role="menuitem" href="#">Item 1</a>
  <a role="menuitem" href="#">Item 2</a>
</div>
```
- The button indicates whether the menu is expanded or collapsed using `aria-expanded`.
- The menu is hidden from assistive technologies when `aria-hidden` is true.
**Modal Dialog:**
```html
<div role="dialog" aria-modal="true" aria-labelledby="dialog-title">
  <h2 id="dialog-title">Dialog Title</h2>
  <p>Dialog content goes here.</p>
  <button aria-label="Close dialog">Close</button>
</div>
```
- The dialog is marked with `role="dialog"` and `aria-modal="true"` to indicate it is a modal.
- The dialog title is associated with the dialog using `aria-labelledby`.
## Accessibility Best Practices
- Use semantic HTML elements whenever possible before resorting to ARIA roles and attributes.
- Ensure that all interactive elements are keyboard accessible.
- Provide clear and descriptive labels for all form controls.
- Use ARIA attributes to enhance accessibility, but avoid overusing them or using them incorrectly.
- Test your website with screen readers and other assistive technologies to ensure a good user experience.
- Follow WCAG (Web Content Accessibility Guidelines) to ensure your website meets accessibility standards.
  - Link to WCAG: https://www.w3.org/WAI/standards-guidelines/wcag/
- Regularly audit your website for accessibility issues using tools like Lighthouse, Axe, or WAVE.
- Educate your team about accessibility and the importance of inclusive design.
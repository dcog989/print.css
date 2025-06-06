# print.css

A comprehensive and customizable CSS stylesheet for creating professional-looking printed web pages. It removes clutter, optimizes for readability, and handles common web components gracefully.

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

## Features

- **Saves Ink:** Resets backgrounds to transparent and removes box shadows.
- **Removes Clutter:** Hides common unneccessary elements like headers, footers, navs, and sidebars.
- **Optimized Layout:** Forces a clean, single-column layout for linear reading.
- **Readable Typography:** Prevents awkward page breaks in headings, images, and lists using `orphans` and `widows`.
- **Smart Links:** Displays the destination URL for external links.
- **Robust Media:** Ensures images don't overflow and that table headers (`<thead>`) repeat on every page.
- **Handles Modern Elements:** Forces `<details>` elements to be open and visible.
- **Highly Customizable:** All key values (fonts, margins, colors) are defined as CSS Variables for easy overriding.

## Usage

Link the stylesheet in your HTML's `<head>`. The `@media print` query is already included in the file, so it will only apply when printing.

```html
<link rel="stylesheet" href="print.css">
```

## Customization

To customize the stylesheet, simply redefine the CSS variables in your own print styles. Ensure your stylesheet is loaded *after* `print.css`.

**Example:**

```css
/* my-styles.css */
@media print {
  :root {
    /* Use a sans-serif font instead of serif */
    --print-font-family: "Helvetica Neue", Helvetica, Arial, sans-serif;
    
    /* Increase the page margin */
    --print-page-margin: 2cm;

    /* Make links blue again */
    --print-link-color: #007bff;
  }
}
```

## Utility Classes

Control element visibility and page breaks directly in your HTML.

- `.no-print` or `[data-print="false"]`: Hides the element from print.
- `.print-only` or `[data-print="only"]`: Shows the element *only* for print.
- `.page-break-before`: Forces a page break before the element.
- `.page-break-after`: Forces a page break after the element.

## License

[MIT](https://opensource.org/licenses/MIT)

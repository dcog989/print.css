# print.css Stylesheet

This repository contains a comprehensive CSS stylesheet designed to optimize web pages for printing.  It's a single `.css` file intended to be included in your project and activated only when the user initiates a print operation (e.g., by pressing Ctrl+P or selecting "Print" from the browser menu).

## Features

*   **Clean and Readable Output:**  Focuses on presenting the core content of a webpage in a clear, legible format, removing unnecessary elements like navigation, advertisements, and interactive components.

*   **Customizable Variables:** Uses CSS variables (`:root`) to allow easy customization of print styles, such as font family, font size, colors, and margins.

*   **Ink Saving Design:**  Defaults to white backgrounds and removes unnecessary background colors and shadows to conserve ink.

*   **Enhanced Typography:**  Optimizes typography for print, ensuring headings, paragraphs, and lists are well-formatted and readable.

*   **Smart Link Handling:**  Displays URLs after links, making them accessible even in printed form.  Excludes URLs for internal links and JavaScript links.

*   **Media Optimization:**  Resizes images to fit the page width and prevents them from overflowing.  Optimizes tables for print with borders and header repetition.

*   **Page Break Control:** Provides classes (`.page-break-before`, `.page-break-after`) for finer control over where page breaks occur.

*   **`no-print` and `print-only` Classes:** Allows you to easily hide elements for printing (`.no-print`) and display elements only when printing (`.print-only`). Also supports the `data-print` attribute for more flexible control.

*   **'details' element handling:** Forces the display of details element when printing.

## Usage

1.  **Download the `print.css` file:**  Clone this repository or download the `print.css` file directly.

2.  **Include the stylesheet in your HTML:**  Add the following `<link>` tag within the `<head>` section of your HTML document:

    ```html
    <link rel="stylesheet" href="path/to/print.css" media="print">
    ```

    **Important:** The `media="print"` attribute ensures that this stylesheet is only applied when printing the page.

3.  **Customize the styles (optional):**  Modify the CSS variables in the `:root` selector within `print.css` to match your website's design and preferences.  For example:

    ```css
    :root {
        --print-font-family: Arial, sans-serif;
        --print-font-size: 11pt;
        --print-link-color: #333;
        --print-page-margin: 1cm;
    }
    ```

4.  **Use `no-print` and `print-only` classes:**

    *   Add the `no-print` class to any element you want to hide when printing:

        ```html
        <nav class="no-print">...</nav>
        ```

    *   Add the `print-only` class to any element you want to display only when printing:

        ```html
        <div class="print-only">Generated on: 2025-04-04</div>
        ```

    *   Use the `data-print` attribute to hide elements when `data-print="false"` or show elements when `data-print="only"`

        ```html
        <p data-print="false">This paragraph will be hidden when printing.</p>
        <div data-print="only">This div will only be visible when printing.</div>
        ```

5.  **Test printing:**  Open your webpage in a browser and initiate the print dialog (Ctrl+P or File > Print).  Review the print preview to ensure the output is as desired.  Adjust the styles in `print.css` as needed.

## Example

```html
<!DOCTYPE html>
<html>
<head>
    <title>My Printable Page</title>
    <link rel="stylesheet" href="style.css">  <!-- Your regular stylesheet -->
    <link rel="stylesheet" href="print.css" media="print"> <!-- Print stylesheet -->
</head>
<body>
    <header class="no-print">
        <h1>My Website</h1>
        <nav>...</nav>
    </header>

    <main>
        <article>
            <h2>Article Title</h2>
            <p>This is the main content of the article.</p>
            <img src="image.jpg" alt="An example image">
            <p>More content...</p>
        </article>
    </main>

    <footer class="no-print">
        <p>&copy; 2023 My Website</p>
    </footer>

    <div class="print-only">
        <p>Printed on: <!-- Add dynamic date here with JS if needed --></p>
    </div>
</body>
</html>
```

## Contributing

Contributions are welcome!  If you find any issues or have suggestions for improvements, please submit a pull request or create an issue.

## License

This project is licensed under the [MIT License](LICENSE). See the `LICENSE` file for more information.

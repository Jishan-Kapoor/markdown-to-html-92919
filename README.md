# README

## Summary
This static web application converts `input.md` to HTML, renders it in `#markdown-output`, and utilizes highlight.js for code blocks.

## Setup
To deploy on GitHub Pages:
1. Fork this repository.
2. Upload `input.md` as an attachment.
3. Enable GitHub Pages in repository settings.

## Usage
- Access the page at `[YourGitHubUsername].github.io/[RepoName]`.
- No query parameters or configuration options needed.
- Key features:
  - Convert `input.md` to HTML.
  - Display the result in `#markdown-output`.
  - Syntax highlighting with highlight.js.

## Code Explanation
The application uses JavaScript to fetch `input.md`, convert it to HTML, and render it on the page.

- Libraries used:
  - highlight.js for code block syntax highlighting.

```javascript
// Fetch input.md content
fetch('input.md')
  .then(response => response.text())
  .then(data => {
    const converter = new showdown.Converter();
    const html = converter.makeHtml(data);
    document.getElementById('markdown-output').innerHTML = html;
    hljs.highlightAll();
});
```

## License
This project is licensed under the MIT License.
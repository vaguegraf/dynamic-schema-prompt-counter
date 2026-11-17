# Dynamic Schema.org Prompt & Code Counter

A lightweight, zero-dependency JavaScript snippet that automatically scans any webpage, counts embedded **prompt/code blocks** and **media examples** (images and videos), and dynamically injects valid **Schema.org JSON-LD** (`ItemPage` + `CreativeWork`) structured data into the `<head>`.

Designed for AI prompt libraries, code snippet blogs, tutorials, and multi-modal showcases (Text-to-Image, Text-to-Video, LLM prompts, and developer docs).

## Features

* **Universal Detection:** Automatically counts code/prompt containers (`<pre>`, `<code>`, custom classes) as well as visual examples (`<img>`, `<video>`).
* **Dynamic SEO & AI Search Indexing:** Generates clean `application/ld+json` structured data and meta keywords on the fly based on the current page title and content.
* **Zero Dependencies:** Pure vanilla JavaScript (~2 KB), works on WordPress, static HTML, Webflow, Ghost, or any custom CMS.
* **Duplicate Safe:** Checks if the JSON-LD tag already exists before injecting.

## Quick Installation

Paste the `<script>` snippet from `schema-prompt-counter.html` right before the closing `</body>` tag (or in your site's **Footer Scripts** section).

## Configuration

Customize the `config` object at the top of the script to match your site's structure:

```javascript
var config = {
    siteSuffix: ' | Your Site Name', // Removed from document.title to extract clean topic name
    contentSelector: 'article, .entry-content, main',
    codeSelector: 'pre, code, .wp-block-code, [class*="prompt"], [class*="code"]',
    mediaSelector: 'img, video',
    workDescription: 'Curated AI prompts, code snippets, and multi-modal generation examples.',
    baseKeywords: 'AI prompts, prompt engineering, code snippets, text-to-image, text-to-video',
    injectMetaKeywords: true
};
```

## License

Released under the [MIT License](LICENSE).

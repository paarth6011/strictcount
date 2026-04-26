# 📝 StrictCount

**StrictCount** is a lightweight, browser-based academic utility designed to accurately calculate the true word count of essays and research papers. It automatically filters out inline citations, references, and structural text (like figure captions) that traditionally inflate academic word counts.

[**🔴 View Live Demo Here**](https://paarth6011.github.io/strictcount/)

## ✨ Features

* **Smart Exclusions:** Uses custom Regular Expressions (Regex) to detect and instantly remove:
  * APA & Harvard in-text citations *(e.g., Smith, 2023)*
  * MLA citations *(e.g., Smith 45)*
  * IEEE & Chicago numbered citations *(e.g., [1] or (1))*
  * Figure and Table captions/mentions *(e.g., Figure 1, as seen in Fig 2)*
* **Multi-Format Support:** Natively parses raw text from both `.docx` and `.pdf` file uploads directly in the browser.
* **Live Verification Visualizer:** Provides a side-by-side terminal view that actively highlights and strikes through the exact text being excluded, ensuring 100% transparency.
* **Smart Boundary Markers:** Allows users to set custom "Start" and "Stop" markers to automatically ignore Title Pages, Abstracts, and Bibliographies.

## 🛠️ Tech Stack

* **Frontend:** HTML5, CSS3, Vanilla JavaScript
* **File Parsing Libraries:** * [`mammoth.js`](https://github.com/mwilliamson/mammoth.js) - For extracting raw text from `.docx` files.
  * [`pdf.js`](https://mozilla.github.io/pdf.js/) (Mozilla) - For parsing and rebuilding paragraphs from `.pdf` coordinates.
* **Deployment:** Fully static and serverless (Hosted on GitHub Pages / Netlify).

## ⚙️ The Technical Challenge: PDF Parsing

Unlike `.docx` files, PDFs do not inherently understand what a "paragraph" or "space" is; they merely plot characters on an X/Y coordinate plane. 

To solve this, StrictCount utilizes a custom PDF extraction script that tracks the vertical `Y-coordinate` of text elements. By calculating the `deltaY` (the gap between lines), the app intelligently determines whether to insert a standard space (sentence wrap) or a double line break (true paragraph), preserving the document's structure for the Regex engine to process accurately.

## 🚀 Running Locally

Because StrictCount is entirely client-side, no backend or database is required. 

1. Clone this repository:
   ```bash
   git clone [https://github.com/your-username/strictcount.git](https://github.com/your-username/strictcount.git)

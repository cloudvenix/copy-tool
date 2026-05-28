# Text Variation & Readability Editor

A client-side, single-page web app for parsing `.docx` documents, introducing controlled stylistic variations, and exporting the result.

Live at: **https://copy.cloudvenix.in**

## Features

- **Parse `.docx`** via [mammoth.js](https://github.com/mwilliamson/mammoth.js) (tables, headings, lists, formatting preserved)
- **Export** as `.docx`, `.html`, or `.txt`
- **Organic imperfection injection** — capitalization variance, article swapping, letter transposition, punctuation drift, double-spacing — with intensity slider (1–100%)
- **Paraphrase** with selectable style (Standard / Formal / Casual / Concise)
- **Tone adjustment** — Simple, Academic, Conversational
- **Complex-word highlighting** with one-click simpler-synonym replacement
- **Find & Replace** with case sensitivity, prev/next navigation, replace all
- **Undo / Redo** stack (50-snapshot history)
- **Selection-aware**: Imperfections, Paraphrase, and Tone act on a text selection if one exists; otherwise the whole document
- **Live stats** — words, characters, sentences, paragraphs, reading time, Flesch-Kincaid grade
- **Drag-and-drop** `.docx` upload
- **Dark mode** (persisted in localStorage)
- **Keyboard shortcuts** (press `?` to see them all)

## Run locally

It's a single HTML file with no build step:

```bash
python -m http.server 8000
# then open http://localhost:8000/
```

## Tech

- HTML5, CSS3, vanilla JavaScript (ES6+)
- [mammoth.js](https://github.com/mwilliamson/mammoth.js) — `.docx` → HTML
- [html-docx-js](https://github.com/evidenceprime/html-docx-js) — HTML → `.docx`
- [FileSaver.js](https://github.com/eligrey/FileSaver.js) — cross-browser blob saving

UI motion inspired by [Emil Kowalski](https://emilkowal.ski/).

## Architecture notes

`paraphraseText(text, style)` and `adjustTone(text, tone)` are intentionally written as `async` mock functions so they can be swapped for a real API call (OpenAI / Anthropic) by replacing the body — see the inline comment under the paraphrase function.

## Deployment

Hosted on GitHub Pages with `CNAME` pointing to `copy.cloudvenix.in`.

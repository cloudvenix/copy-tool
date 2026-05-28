# Project Configuration

## Auto-Approval Policy

**YES to all changes.** Proceed with all modifications, file creations, edits, and commands without waiting for user confirmation.

- Auto-approve file creation
- Auto-approve file edits
- Auto-approve dependency installations
- Auto-approve running development servers
- Auto-approve running localhost
- Auto-approve any code modifications
- No need to ask "should I proceed?" — just proceed

## Project Notes

This is a client-side web application: **Text Variation and Readability Editor**.

### Stack
- HTML5, CSS3, Vanilla JavaScript (ES6+)
- mammoth.js (CDN) for .docx parsing
- Single-page application, runs on localhost via Python's http.server or Node's http-server

### Conventions
- Single file preferred where practical
- Heavy commenting required
- Robust error handling for invalid file uploads
- Structure mock async functions cleanly so they can be swapped for real API calls (OpenAI / Anthropic) later

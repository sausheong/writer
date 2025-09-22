# Writer

A web-based text editor with AI agent capabilities for writing and editing files.

## Features

- **File Management**: Browse, create, and edit files in the browser's Origin Private File System (OPFS).
- **Multi-Tab Editing**: Open multiple files simultaneously; unsaved changes are preserved when switching tabs.
- **AI Assistance**: Integrated AI agent using Google's Gemini models for text editing and generation.
  - Streaming responses for real-time feedback.
  - Configurable auto-apply suggestions to the editor.
  - Stop button to cancel ongoing requests.
- **Markdown Preview**: Live preview of markdown files with typography styling.
- **Find & Replace**: Search and replace within text files with visual highlighting.
- **Dirty State Tracking**: Visual indicators (amber tabs) for unsaved files.
- **Keyboard Shortcuts**: Cmd/Ctrl+S to save, Cmd/Ctrl+F to find, Cmd+Enter to send AI prompts.
- **Popout Preview**: Detach the preview into a separate window.
- **Settings**: Configure API key, model, streaming, auto-apply, and preferences in a modal.
- **File Highlighting**: Currently selected file is highlighted in the file tree.

## Requirements

- A modern web browser supporting OPFS (e.g., Chrome, Edge).
- Google Gemini API key for AI features.

## Installation and Running

1. **Standalone Usage**: `index.html` can be used standalone by opening it directly in a web browser. No backend required; all storage is local via OPFS.

2. **Local Server**: For development or serving, you can use any web server. For example, on macOS, set up a local Apache server on port 80 and start it locally by following [these instructions](https://medium.com/@sausheong/how-to-set-up-a-local-web-server-on-macos-15-sequoia-90a70293ce74).

3. **With Go Server**: Alternatively, clone the repository, ensure Go is installed, and run:
   ```
   go run main.go
   ```
   Then open `http://localhost:12345` in your browser.

## Usage

- **File Operations**: Use the left panel to browse and create files/folders. Newly created files are automatically selected.
- **Editing**: Select a file to edit in the middle panel. The selected file is highlighted in the file tree.
- **AI Agent**: In the right panel, enter prompts like "rewrite this paragraph" and get AI suggestions. Use the stop button to cancel requests.
- **Settings**: Click the gear (⚙️) icon to configure your Gemini API key, model, streaming mode, and auto-apply preferences.
- **Saving**: Press Cmd+S (macOS) or Ctrl+S (Windows/Linux) to save.
- **Find/Replace**: Press Cmd+F to open find panel; use Shift+Enter for previous matches, Enter for next.

Note: Files are stored in the browser's OPFS, so they persist across sessions but are local to the browser.

## Technology Stack

- **Frontend**: HTML, Tailwind CSS, DaisyUI, JavaScript (ES6+)
- **Libraries**: Marked.js for markdown parsing, Fetch API for HTTP requests
- **AI**: Google Gemini API (models: gemini-2.5-flash, gemini-2.5-pro)
- **Storage**: Origin Private File System (OPFS)

## Contributing

Contributions are welcome! Please open issues or submit pull requests.

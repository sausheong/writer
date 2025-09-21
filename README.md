# Writer

A web-based text editor with AI agent capabilities for writing and editing files.

## Features

- **File Management**: Browse, create, and edit files in the browser's Origin Private File System (OPFS).
- **Multi-Tab Editing**: Open multiple files simultaneously; unsaved changes are preserved when switching tabs.
- **AI Assistance**: Integrated AI agent using Google's Gemini models for text editing and generation.
  - Streaming-only responses for real-time feedback.
  - Safeguard prevents overwriting files with empty AI output.
- **Markdown Preview**: Live preview of markdown files with typography styling.
- **Dirty State Tracking**: Visual indicators (amber tabs) for unsaved files.
- **Keyboard Shortcuts**:
  - Cmd/Ctrl+S: Save current file
  - Cmd/Ctrl+F: Open Find/Replace panel; press again to toggle focus between Find and Replace
  - Enter / Shift+Enter (in Find): Next / Previous match
  - Enter (in Replace): Replace current; use "Replace All" to replace all matches
  - Cmd/Ctrl+Enter (in AI input): Send prompt to AI
- **Popout Preview**: Detach the preview into a separate window.
- **Settings**: Configure Google API key and model in a modal.

## Requirements

- Go 1.x or later
- A modern web browser supporting OPFS (e.g., Chrome, Edge)
- Google API key for Gemini (Generative Language API)

## Installation and Running Standalone

1. **Standalone Usage**: `index.html` can be used standalone by placing it in any web server. There's no dependency on the backend Go server; it's there simply to host the file.

2. **Local Setup**: You can run it on your local machine. For example, on macOS, set up a local Apache server on port 80 and start it locally anytime by following [these instructions](https://medium.com/@sausheong/how-to-set-up-a-local-web-server-on-macos-15-sequoia-90a70293ce74).

3. **With Go Server**: Alternatively, clone the repository, ensure Go is installed, and run:
   ```
   go run main.go
   ```
   Then open `http://localhost:12345` in your browser.

## Usage

- **File Operations**: Use the left panel to browse and create files/folders.
- **Editing**: Select a file to edit in the middle panel.
- **AI Agent**: In the right panel, enter prompts like "rewrite this paragraph" and get AI suggestions. Press Cmd/Ctrl+Enter to send.
- **Settings**: Click the gear (⚙️) icon to configure your Google API key and model preferences.
- **Find/Replace**: Press Cmd/Ctrl+F to open. Enter toggles next, Shift+Enter toggles previous. Enter in Replace performs a single replacement; "Replace All" replaces all.
- **Saving**: Press Cmd+S (macOS) or Ctrl+S (Windows/Linux) to save.

Note: Files are stored in the browser's OPFS, so they persist across sessions but remain local to the browser and device.

## Technology Stack

- **Backend**: Go (simple HTTP server)
- **Frontend**: HTML, Tailwind CSS, DaisyUI, JavaScript
- **Libraries**: Marked.js for markdown parsing
- **AI**: Google Generative Language API (Gemini 2.5 models: `gemini-2.5-flash` default, optional `gemini-2.5-pro`)
- **Storage**: Origin Private File System (OPFS)

## Contributing

Contributions are welcome! Please open issues or submit pull requests.


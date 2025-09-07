# Writer

A web-based text editor with AI agent capabilities for writing and editing files.

## Features

- **File Management**: Browse, create, and edit files in the browser's Origin Private File System (OPFS).
- **Multi-Tab Editing**: Open multiple files simultaneously; unsaved changes are preserved when switching tabs.
- **AI Assistance**: Integrated AI agent using OpenAI's GPT-5 models for text editing and generation.
  - Streaming responses for real-time feedback.
  - Auto-apply suggestions to the editor.
- **Markdown Preview**: Live preview of markdown files with typography styling.
- **Dirty State Tracking**: Visual indicators (amber tabs) for unsaved files.
- **Keyboard Shortcuts**: Cmd/Ctrl+S to save files.
- **Popout Preview**: Detach the preview into a separate window.
- **Settings**: Configure API key, model, and preferences in a modal.

## Requirements

- Go 1.x or later
- A modern web browser supporting OPFS (e.g., Chrome, Edge)
- OpenAI API key for AI features

## Installation and Running Standalone

1. **Standalone Usage**: `writer.html` can be used standalone by placing it in any web server. There's no dependency on the backend Go server; it's there simply to host the file.

2. **Local Setup**: You can run it on your local machine. For example, on macOS, set up a local Apache server on port 80 and start it locally anytime by following [these instructions](https://medium.com/@sausheong/how-to-set-up-a-local-web-server-on-macos-15-sequoia-90a70293ce74).

3. **With Go Server**: Alternatively, clone the repository, ensure Go is installed, and run:
   ```
   go run main.go
   ```
   Then open `http://localhost:12345` in your browser.

## Usage

- **File Operations**: Use the left panel to browse and create files/folders.
- **Editing**: Select a file to edit in the middle panel.
- **AI Agent**: In the right panel, enter prompts like "rewrite this paragraph" and get AI suggestions.
- **Settings**: Click the gear (⚙️) icon to configure your OpenAI API key and model preferences.
- **Saving**: Press Cmd+S (macOS) or Ctrl+S (Windows/Linux) to save.

Note: Files are stored in the browser's OPFS, so they persist across sessions but are local to the browser.

## Technology Stack

- **Backend**: Go (simple HTTP server)
- **Frontend**: HTML, Tailwind CSS, DaisyUI, JavaScript
- **Libraries**: Marked.js for markdown parsing
- **AI**: OpenAI Responses API with GPT-5 models
- **Storage**: Origin Private File System (OPFS)

## Contributing

Contributions are welcome! Please open issues or submit pull requests.


# md2xmind for VS Code

Convert your Markdown outlines into Xmind mind maps directly within VS Code.

## Features

- **AI Extraction**: Use the VS Code Language Model API to automatically extract key concepts from any file into a nested mind map.
- **Hierarchical Nesting**: H1-H6 headings are correctly nested in the Xmind tree.
- **Task Support**: Markdown checkboxes `- [ ]` and `- [x]` map to Xmind task markers.
- **Notes & Links**: Indented paragraphs and Markdown links are preserved as Xmind notes and hyperlinks.
- **Labels**: Tags in format `[Label] Text` are converted to Xmind labels.
- **Styling**: Default to use the "Kimono" theme with automated multi-line colors.

## Usage

This extension provides several commands to generate Xmind mind maps.

### Available Commands

| Command | Description |
|---------|-------------|
| **Export to Xmind** | Directly converts a Markdown file (`.md`) into an Xmind file. |
| **Create mind map with AI** | Uses AI to extract key concepts from *any* file (PDF, text, code, etc.) into a structured mind map. Generates an intermediate `.ai.md` file and exports it to Xmind. |

### How to Run

You can invoke these commands from three different places in VS Code:

#### 1. Explorer Context Menu
- Right-click a file in the **Explorer** sidebar.
- Select **md2xmind: Export to Xmind** (for `.md` files) or **md2xmind: Create mind map with AI** (for any file type).

#### 2. Editor Context Menu
- Right-click anywhere inside an open document.
- Select **md2xmind: Export to Xmind** (for `.md` files) or **md2xmind: Create mind map with AI** (for any file type).

#### 3. Command Palette
1. Press `Cmd+Shift+P` (macOS) or `Ctrl+Shift+P` (Windows/Linux).
2. Type `md2xmind`.
3. Select either **md2xmind: Export to Xmind** or **md2xmind: Create mind map with AI**.

---

## Requirements

No external dependencies are required. This extension bundles the necessary logic to generate Xmind files (standard `.xmind` format compatible with Xmind 2020+).

## Extension Settings

This extension contributes the following settings:

* `md2xmind.exportOnSave`: Automatically export to Xmind whenever you save a Markdown file (Default: `false`).
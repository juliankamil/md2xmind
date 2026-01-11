# md2xmind for VS Code

Convert your Markdown outlines into Xmind mind maps directly within VS Code.

## Features

- **Hierarchical Nesting**: H1-H6 headings are correctly nested in the Xmind tree.
- **Task Support**: Markdown checkboxes `- [ ]` and `- [x]` map to Xmind task markers.
- **Notes & Links**: Indented paragraphs and Markdown links are preserved as Xmind notes and hyperlinks.
- **Labels**: Tags in format `[Label] Text` are converted to Xmind labels.
- **Styling**: Default to use the "Kimono" theme with automated multi-line colors.

## Usage

There are three ways you can run the extension to convert Markdown outlines into Xmind mind maps:

### 1. Right-click Menu (Explorer)
- Right-click any `.md` file in the Explorer and select **md2xmind: Export to Xmind**. The `.xmind` file will be created in the same directory.

### 2. Context Menu (Editor)
- Right-click anywhere inside an open Markdown file and select **md2xmind: Export to Xmind**.

### 3. Command Palette
1. Open a Markdown file.
2. Press `Cmd+Shift+P` (macOS) or `Ctrl+Shift+P` (Windows/Linux).
3. Type `md2xmind` and select **md2xmind: Export to Xmind**.

## Requirements

No external dependencies are required. This extension bundles the necessary logic to generate Xmind files (standard `.xmind` format compatible with Xmind 2020+).

## Extension Settings

This extension contributes the following settings:

* `md2xmind.exportOnSave`: (Coming soon) Automatically export to Xmind whenever you save a Markdown file.

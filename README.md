# md2xmind for VS Code

Convert your Markdown outlines into Xmind mind maps directly within VS Code.

## Features

- **AI Extraction**: Use the VS Code Language Model API (Copilot) or local LLMs (Ollama, LM Studio) to automatically extract key concepts from any file into a nested mind map.
- **Local AI Support**: Seamlessly integrate with Ollama and LM Studio for private, offline, and cost-effective extraction.
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
| **Change AI Model** | Clears the cached AI model preference so you can select a different one on next use. |
| **Refresh AI Models** | Re-scans for available local AI services (Ollama, LM Studio). |
| **Test AI Connection** | Verifies connectivity to the currently selected AI model/service. |

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
3. Select any of the available **md2xmind** commands.

## Extension Settings

This extension contributes the following settings:

* `md2xmind.exportOnSave`: Automatically export to Xmind whenever you save a Markdown file (Default: `false`).
* `md2xmind.ai.systemPrompt`: Custom system prompt for AI Mind Map extraction. If empty, the internal default is used. Overridden by `.vscode/md2xmind.prompt.md` if present in the workspace.
* `md2xmind.ai.local.ollamaUrl`: Base URL for Ollama API (Default: `http://localhost:11434/v1`).
* `md2xmind.ai.local.lmStudioUrl`: Base URL for LM Studio API (Default: `http://localhost:1234/v1`).
* `md2xmind.ai.local.contextWindow`: Conservative token limit for local AI models (Default: `4096`).

## Local AI Support (Ollama & LM Studio)

You can use local LLMs for mind map extraction to ensure privacy and offline availability.

1.  **Start your local service**: Ensure Ollama or LM Studio is running on your machine.
2.  **Model Discovery**: When you run **Create mind map with AI**, the extension will automatically attempt to discover models from your local services.
3.  **Unified Picker**: Select your preferred model from the grouped list (VS Code vs. Ollama vs. LM Studio).
4.  **Verification**: Use **md2xmind: Test AI Connection** to verify that the extension can communicate with your selected local model.

## Custom AI Prompts

You can customize how the AI extracts information by providing a custom system prompt. The extension uses a tiered resolution strategy:

1.  **Workspace File**: Create a file at `.vscode/md2xmind.prompt.md` in your workspace. This allows for project-specific extraction rules with full Markdown highlighting while editing the prompt.
2.  **User Settings**: Configure the `md2xmind.ai.systemPrompt` setting in your VS Code settings.
3.  **Default**: If neither of the above are provided, a built-in expert mind-mapping prompt is used.

The progress notification will indicate which prompt source is being used during execution (e.g., "Extracting... (workspace prompt)").

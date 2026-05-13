# MTCode AI Phoenix

AI-powered code completion and chat for VS Code — connect to your own LLM server and get intelligent suggestions as you type.

## Quick Start

Visit [mtcodeai.com](https://mtcodeai.com) to download the MTCode Server package that matches your GPU brand (Nvidia, AMD, and more to come). **For the administrator** who sets up the server:

1. **Set Up an LLM Server** — Install MTCode Server on the GPU machine. On first launch, click **Create an account** in the login dialog to register your administrator account. Sign in, select the built-in LLM server, and pick a coding assistant model (such as Qwen2.5-Coder or Qwen3-Coder) that fits your GPU's VRAM. The server will download the model automatically and be ready to serve requests. The server runs on a private network behind a firewall — the [MTCode DirectLink](https://mtcodeai.com/platform/index.html) platform handles connectivity, allowing authorized users to reach it from anywhere on the internet without any port forwarding or VPN.
2. **Invite Users** — In the administrator account, send invitation emails to the users who will access the LLM server. Each user follows the link in the email to create their own account.

**For each user:**

3. **Install the Extension** — Install MTCode AI Phoenix from the VS Code Marketplace.
4. **Connect** — Open the AI Phoenix sidebar and click **Login** to enter your user account credentials. The server dropdown lists all LLM servers you have been authorized to use. Select one; the status shows **"Server Ready"** when the connection is established and the model is compatible.
5. **Start Coding** — AI completions appear automatically as you type. Press `Tab` to accept, `Escape` to dismiss. Use the chat panel to ask questions or generate code snippets.

## Features

### Inline Code Completion

- **Automatic triggering** — suggestions appear as you type with a configurable delay
- **Fill-in-the-Middle (FIM)** — the model sees code before and after your cursor for context-aware predictions
- **Smart caching** — repeated requests at the same location return cached results instantly
- **Quick toggle** — click the check button on the extension title bar to turn completions on or off

**Keyboard shortcuts:**
- `Tab` — accept full suggestion
- `Shift+Tab` — accept first line only
- `Ctrl+Right` — accept first word
- `Escape` — dismiss

### AI Chat

- **Markdown & syntax highlighting** — responses render with formatted code blocks (C, C++, Python, JavaScript, Markdown)
- **Streaming responses** — answers appear word by word in real time
- **Automatic context** — the active editor file is used as context; switch files and context switches automatically
- **Additional context files** — attach extra files for the AI to reference
- **Conversation history** — manage and revisit previous conversations

![MTCode AI Phoenix — AI chat panel on the right with inline code completion as gray ghost text at the cursor in the editor](resources/MTCode-ai-phoenix-UI.png)
*AI chat panel on the right with Markdown-formatted responses, and inline code completion shown as gray ghost text at the cursor position in the editor*

### Private, Self-Hosted & Free

Both the extension and the MTCode Server are free of charge. Your code never leaves your network — all data is transmitted directly over an encrypted connection. No cloud subscriptions, no data sharing with third parties.

## Model Compatibility

| Model Family | Status | Notes |
|---|---|---|
| **Qwen2.5-Coder** | Extensively Tested | Recommended. Excellent completion and chat quality. |
| **Qwen3-Coder** | Extensively Tested | Recommended. Latest generation with improved reasoning. |
| **DeepSeek-Coder** | Limited Testing | Functional with positive results. |
| **Other GGUF models** | Varies | Any GGUF model supported by llama.cpp that uses the same prompt template as the Qwen model should work. |

**Tip:** Use a code-specialized model (e.g., Qwen2.5-Coder-14B-Instruct, Qwen2.5-Coder-7B-Instruct, Qwen3-Coder-Next, or Qwen3-Coder-30B-A3B-Instruct) that fits your GPU's VRAM. Larger models produce better results but require more memory and GPU computing power.

## Configuration

Click the gear icon on the extension title bar to open settings.

- **Enable/disable** — turn completions on or off globally or per language
- **Auto trigger** — automatic suggestions as you type, or manual only
- **Max tokens** — tokens per suggestion (roughly 1 token per 4 characters)
- **Context size** — lines of code before and after cursor sent to the model
- **Completion delay** — delay before sending a request to avoid interrupting rapid typing
- **Request timeout** — maximum wait time for a server response

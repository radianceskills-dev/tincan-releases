<div align="center">

<img src="https://tincan-about.netlify.app/tincan-icon-128.png" alt="TinCan Logo" width="96" height="96" />

# TinCan — Native Android AI Agent & Coding Workspace

**Run a local Alpine Linux sandbox, manage remote SSH servers, connect MCP tools, run offline `.gguf` & Whisper models, and switch OAuth accounts without losing your chat history—natively on your phone.**

[![Latest Release](https://img.shields.io/github/v/release/radianceskills-dev/tincan-releases?style=for-the-badge&label=Latest%20Release&color=10b981)](https://github.com/radianceskills-dev/tincan-releases/releases/latest)
[![Total Downloads](https://img.shields.io/github/downloads/radianceskills-dev/tincan-releases/total?style=for-the-badge&label=Downloads&color=38bdf8)](https://github.com/radianceskills-dev/tincan-releases/releases/latest)
[![Platform Android](https://img.shields.io/badge/Android-7.0%2B%20(ARM64)-3ddc84?style=for-the-badge&logo=android&logoColor=white)](https://github.com/radianceskills-dev/tincan-releases/releases/latest)
[![GitHub Stars](https://img.shields.io/github/stars/radianceskills-dev/tincan-releases?style=for-the-badge&color=f59e0b)](https://github.com/radianceskills-dev/tincan-releases/stargazers)

[**🌐 Official Website**](https://tincan-about.netlify.app) · [**✦ Interactive 3D Tour**](https://tincan-about.netlify.app/experience/) · [**📦 All Releases**](https://github.com/radianceskills-dev/tincan-releases/releases) · [**🐛 Report Issue / Request Feature**](https://github.com/radianceskills-dev/tincan-releases/issues)

---

### ⬇️ Direct One-Click Downloads (Latest: `v2.13.2` · ARM64)

| Package Option | Direct Download Link | Size | When to Use |
| :--- | :--- | :--- | :--- |
| **📱 Direct Android APK** | [**⬇️ Download `TinCan-v2.apk`**](https://github.com/radianceskills-dev/tincan-releases/releases/download/v2.13.2/TinCan-v2.apk) | `59.6 MB` | Standard direct installation on Android 7.0+ (`arm64-v8a`) |
| **📦 ZIP Archive (APK Inside)** | [**⬇️ Download `TinCan-v2-Android-APK.zip`**](https://github.com/radianceskills-dev/tincan-releases/releases/download/v2.13.2/TinCan-v2-Android-APK.zip) | `54.5 MB` | Use if Chrome on Android pauses at 100% while scanning `.apk` files |

> ⭐ **If TinCan helps your mobile workflow, please click the [Star](https://github.com/radianceskills-dev/tincan-releases) button at the top right!** Stars help other Android developers, self-hosters, and AI engineers discover the project.

</div>

---

<div align="center">
  <img src="https://tincan-about.netlify.app/og-card.png" alt="TinCan — Android-Native AI Agent Harness" width="100%" />
</div>

---

## 🚀 Why TinCan?

Most mobile AI apps trap your model inside a text bubble. You can't execute shell scripts, you can't inspect device files, you can't SSH into your servers, and if your free-tier account hits a rate limit, switching accounts wipes your conversation context.

**TinCan (`com.shunmin.tincan`) is a Claude Code-level agentic workspace built natively for Android:**

| Capability | Standard Mobile Chat Apps | **TinCan (Android Agent Workspace)** |
| :--- | :---: | :--- |
| **Local Linux Execution** | ❌ None | ✅ **On-device Alpine Linux sandbox (`proot`)** with `apk` package manager UI & `/mnt/shared` storage mount |
| **Remote Server Access** | ❌ None | ✅ **Built-in multi-host SSH client** + durable **Conch** background jobs that survive disconnects |
| **OAuth Account Switching** | ❌ New account = new chat | ✅ **Switch ChatGPT / Antigravity / Puter / OpenRouter OAuth mid-thread** and resume the exact same conversation |
| **Offline On-Device AI** | ❌ Cloud-only | ✅ **Local `llama.cpp` (`.gguf` + `mmproj` vision)** & offline **Local Whisper** speech-to-text |
| **External Tools & Skills** | ❌ Closed ecosystem | ✅ **Model Context Protocol (MCP)** client (HTTP/SSE + OAuth) & direct **`skills.sh`** skill installer |
| **Reasoning & Critique** | ❌ Single-pass replies | ✅ **Pro Mode** (`Initial Answer → Challenge → Final Answer → Implement → Loop`), **Plan Mode**, & **Build Mode** |
| **Voice & Multimodal Profiles** | ❌ Single fixed engine | ✅ **Multi-provider saved profiles** for STT (editable voice draft), TTS (Android + AI TTS), and Image Gen/Edit |
| **Automation & Memory** | ❌ Manual prompts only | ✅ **5-field Cron background tasks**, in-chat **Loops**, two-tier **Persistent Memory**, & **Semantic RAG** |

---

## 🛠️ Complete Feature Reference

### 1. Code Execution & Infrastructure (`Linux Sandbox` + `SSH`)
- **On-Device Alpine Linux Sandbox (`proot`):** Execute shell commands, run Python/Node/Bash scripts, manage Alpine packages via a dedicated UI, and configure custom environment variables.
- **Shared Android Storage (`/mnt/shared`):** Optionally mount your device's shared storage directly inside the Linux sandbox to inspect, generate, or process local files.
- **Multi-Host Remote SSH:** Connect your home lab, VPS, or cloud servers over SSH. Your agent can run remote commands and `read`, `write`, `edit`, `grep`, and `glob` remote files directly from chat.
- **Durable Background Jobs (Conch):** Launch long-running shell commands that continue executing in the background even if your mobile network drops.

### 2. Models, OAuth & Seamless Account-Switch Resume
- **One-Tap OAuth Sign-In:** Built-in OAuth support for **OpenAI (ChatGPT)**, **Antigravity / Google**, **Puter**, and **OpenRouter**—works even on free tiers.
- **Zero-Loss Account Switching:** Because conversations and memory live locally on your phone, hitting a usage cap on one account lets you switch OAuth accounts (or swap to an API key / local model) and **resume the exact same conversation thread**.
- **On-Device Offline LLM Inference (`llama.cpp`):** Run quantized `.gguf` chat models and multimodal vision (`mmproj`) projectors 100% offline on your Android CPU/GPU.
- **BYOK & Custom Endpoints:** Add multiple API keys, custom base URLs, OpenAI Responses API endpoints, service-tier selection, model aliases, and granular sampler controls (`thinking_budget`, `temperature`, `top_p`, `min_p`, `max_tokens`).

### 3. Agent Modes & Deliberate Reasoning
- **Chat Mode:** Fast, tool-enabled conversational assistant.
- **Plan Mode (Read-Only):** Safely inspect files, servers, and architecture without modifying any files or external state.
- **Build / Agent Mode:** Autonomous multi-step execution across shell, files, web, and MCP tools.
- **Pro Mode (5-Stage Self-Critique Loop):**
  ```text
  01 Initial Answer  ──►  02 Challenge Assumptions  ──►  03 Final Answer  ──►  04 Implement  ──►  05 Loop ↺
  ```
- **Agent & Prompt Templates:** Built-in and custom templates for software engineering, DevOps, research, data analysis, and office workflows, plus reusable prompt templates with variables.

### 4. MCP Servers, `skills.sh` & Web Research
- **Model Context Protocol (MCP) Client:** Connect pre-configured or custom HTTP/SSE MCP servers with custom headers and OAuth client credentials.
- **Direct `skills.sh` Integration:** Browse, install, update, and manage modular agent skills directly inside the app.
- **Web Search & Full-Page Web Fetch:** Give any cloud or local model live web search and clean Markdown extraction from URLs.

### 5. Multi-Profile Voice (Local Whisper), TTS, Vision & Media
- **Multi-Provider Profiles:** Save and switch between multiple provider profiles for **Audio Transcription (STT)**, **Text-to-Speech (TTS)**, and **Image Generation**.
- **Audio Transcription into Editable Drafts:** Record speech using offline **Local Whisper** models or cloud STT providers. Transcripts always land in an editable draft first—never sent automatically by mistake.
- **Read Aloud (Android System TTS + AI TTS):** Uses zero-latency Android system TTS by default, with optional custom AI TTS profiles.
- **Image Generation & Reference Editing:** Generate images from text prompts or attach reference images in chat to guide visual edits.
- **Vision Bridge (Image Transcription):** Automatically describe attached images using a dedicated vision model when chatting with a text-only LLM.
- **Video Frame Slicer & PDF Page Selector:** Slice videos by time range/interval and preview/select specific PDF pages before sending.

### 6. Two-Tier Persistent Memory, Semantic RAG & Automation
- **Two-Tier Memory Architecture:** Combines an always-injected **Active Memory** core with a searchable **Memory Files** database (`create`, `read`, `edit`, `search`, `delete`).
- **Semantic RAG Conversation Search:** Search across all past conversations using keywords or vector embeddings.
- **Working Memory & Context Compaction:** Real-time token/cost breakdown, automatic context compaction, and durable bounded slices for large tool outputs.
- **5-Field Cron Tasks & In-Chat Loops:** Schedule recurring background tasks with standard cron expressions and notifications, or run timed autonomous loops (`10s` to `7d` intervals) inside an active thread.

### 7. Collaboration, Portability & Network Privacy
- **Whole-Conversation Sharing & Branching Forks:** Share complete conversation branches externally with full context, or fork any conversation to explore a different approach without altering the original.
- **ChatGPT & Claude History Import:** Import your existing conversation exports from ChatGPT and Claude, or configure automated local TinCan backups.
- **HTTP & SOCKS Proxy Support:** Route all app and model traffic through custom HTTP or SOCKS proxies with authentication and bypass rules.

---

## 📲 Installation & Verification

1. Download either [**`TinCan-v2.apk`**](https://github.com/radianceskills-dev/tincan-releases/releases/download/v2.13.2/TinCan-v2.apk) or [**`TinCan-v2-Android-APK.zip`**](https://github.com/radianceskills-dev/tincan-releases/releases/download/v2.13.2/TinCan-v2-Android-APK.zip) (if downloading the `.zip`, extract `TinCan v2.apk` first).
2. Open the `.apk` file on your Android device (requires **Android 7.0+** on **ARM64 / `arm64-v8a`**).
3. Verify your download checksum (optional):
   ```text
   Version:  2.13.2 (versionCode 57)
   Package:  com.shunmin.tincan
   APK SHA-256: cb7581b8bf5d32adeb738e23da460aeff7bfff121c1303dac9e0bbb3640a55fb
   ZIP SHA-256: 329765aeefd4aea318a8466e10e729cb757bf8a39decd0870d69e38a5259c5da
   ```

---

## 🔍 Search Keywords & Topics

`android ai agent` · `claude code android` · `mobile coding agent` · `mcp client android` · `model context protocol mobile` · `alpine linux sandbox android` · `proot linux ai agent` · `ssh ai agent` · `local llm android gguf` · `llama.cpp android` · `offline whisper android` · `chatgpt oauth android` · `antigravity oauth` · `puter ai` · `openrouter android client` · `skills.sh`

---

<div align="center">

**Built for developers, self-hosters, and power users who want a real AI engineering workspace in their pocket.**

[**⬇️ Download Latest APK (`v2.13.2`)**](https://github.com/radianceskills-dev/tincan-releases/releases/download/v2.13.2/TinCan-v2.apk) · [**📦 Download ZIP Archive**](https://github.com/radianceskills-dev/tincan-releases/releases/download/v2.13.2/TinCan-v2-Android-APK.zip) · [**🌐 Visit Website**](https://tincan-about.netlify.app)

If you find TinCan useful, please give this repository a ⭐ **Star**!

</div>

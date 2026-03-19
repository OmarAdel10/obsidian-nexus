# Obsidian Nexus Extension

**The Intelligence Bridge between your Code and your Second Brain.**

Obsidian Nexus turns your Obsidian vault into an "Infinite Memory" command center for agentic development. It provides a standardized framework for persistent developer identity, live project roadmaps, and surgical codebase documentation.

## 🚀 Features

- **Zero-Config Initialization**: Automatically creates your project's folder structure and core templates in your vault.
- **Identity Handshake**: Establishes your developer persona and hard preferences at the start of every session.
- **Project Brain**: Maintains a live synchronization of your roadmap, architecture, and milestones.
- **Deep Scouting**: Surgical, line-by-line codebase investigation that traces dependencies and "dumps" the full context into organized vault folders.
- **Visual Mapping**: Automatically generates JSON Canvas maps of your project structure.
- **CLI Control**: Directly control your vault (search, read, create notes) via integrated Obsidian CLI tools.
- **Persistent Plans**: Mandates that all implementation plans are saved to your vault for long-term persistence.

## 📁 Installation

```bash
gemini extension install https://github.com/OmarAdel10/obsidian-nexus.git
```

_Note: During installation, you will be prompted for your `vault_path` and `project_name` (e.g., `G:\Obsidian` and `MyProject`) (WithOut Double/Single Quotes)._

## 📂 Vault Structure

The extension organizes your vault under a `[ProjectName]/` root:

```
VaultRoot/[ProjectName]/
├── Identity/ (Developer Profile)
├── Brain/ (Roadmap, Architecture, Features)
├── Journal/ (Daily Session Logs)
├── Plans/ (Implementation Plans)
└── Templates/ (Session & Brain Templates)
```

## 🔄 Standard Workflow

To get the most out of Obsidian Nexus, you MUST follow this sequence:

1. **Onboarding (`scout full`)**: Run this first on any new project. It **automatically creates your folders**, generates your templates, and maps the high-level architecture.
2. **Indexing (`scout feature <path>`)**: After onboarding, run this for each major feature folder. This performs the deep, line-by-line documentation.
3. **Daily Maintenance (`nexus-sync`)**:
    - **Start of Session**: Run `Handshake` to load your identity and project state.
    - **End of Session**: Run `Summarize` to save your daily logs and update the brain.

## 📜 Skills & Commands

- **`nexus-sync`**: Handles daily `Handshake` (start) and `Summarize` (end).
- **`nexus-scout`**: Performs `scout full` (initialization) or `scout feature` (deep dive).
- **`shared-skills`**: Advanced support for **Markdown** (callouts), **Canvas** (visual maps), and **Bases** (database views).

## 🛠️ Requirements

- **Obsidian**: Must be open for CLI-based tools (search, read, create) to function.

## License

MIT

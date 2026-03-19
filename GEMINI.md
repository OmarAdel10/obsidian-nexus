# Obsidian Nexus - System Instructions

This file defines the operating protocols for the Obsidian Nexus extension. It ensures that any agentic workflow using this extension maintains a persistent "Second Brain" and utilizes the Obsidian CLI effectively.

## 0. Mandatory Workflow Sequence

To ensure context integrity, you MUST follow this order when onboarding a project:
1.  **Full Scan**: Execute `nexus scout full` before any feature-specific work to establish the project roadmap.
2.  **Feature Index**: Execute `nexus scout feature <path>` for relevant directories to gain deep technical context.
3.  **Daily Sync**: Perform the `nexus handshake` at the start of every session and `Summarize` at the end.

## 1. The Nexus Workflow (Memory & Persistence)

### Identity & Project Handshake
- **Mandatory**: At the start of every session, you MUST run the `nexus handshake` protocol.
- **Identity**: Read `${settings.vault_path}\${settings.project_name}\Identity\Developer Profile.md` to load the user's persona and coding preferences.
- **Roadmap**: Read `${settings.vault_path}\${settings.project_name}\Brain\${settings.project_name} Brain.md` and `Architecture.md`.
- **Status**: Check the `Plans/` directory for active implementation plans.

### Session Persistence
- **Summarization**: At the end of every session, you MUST create a daily note in `${settings.vault_path}\${settings.project_name}\Journal\` using the format `DD-MM-YYYY [Session Name].md`.
- **Templates**: Follow the structure defined in `${settings.vault_path}\${settings.project_name}\Templates\Session Log Template.md`.

## 2. Obsidian CLI Tool Usage

Use the `obsidian` CLI tools to interact with a running Obsidian instance. **Requires Obsidian to be open.**

### Syntax & Patterns
- **Parameters**: Use `=` for values. Quote values with spaces: `obsidian_create(name="My Note", content="Hello")`.
- **File Targeting**: 
    - `file=<name>`: Resolves like a wikiNexus (no path needed).
    - `path=<path>`: Exact path from vault root.
- **Vault Targeting**: Use `vault=<name>` as the first parameter to target a specific vault.

### Common Tool Usage
- **Search**: Use `obsidian_search(query="term")` to find content within the actual Obsidian engine.
- **Read**: Use `obsidian_read(file="Note Name")`.
- **Properties**: Use `obsidian_property_set` to update frontmatter metadata.

## 3. Deep Scouting (Codebase Mapping)

- **Scout Full**: Use to initialize a project. Maps the file tree, audits dependencies, and generates the `Architecture.md`.
- **Scout Feature**: Use for surgical deep-dives. Analyze every line of a folder and trace ALL project-local dependencies line-by-line.

## 4. Advanced Markdown Standards

- **Callouts**: Use `> [!type]` for highlights (e.g., `[!info]`, `[!bug]`).
- **Nexuss**: Prefer `[[WikiNexuss]]` for internal vault connections.
- **Canvas**: Use the `json-canvas` skill to generate visual maps of codebase logic.

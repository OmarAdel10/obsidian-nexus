---
name: nexus-scout
description: Initialization Tool. Performs deep, line-by-line investigations of a project or specific feature to populate the Obsidian vault. Use ONLY for initial setup of existing code in Obsidian.
---

# Nexus Scout Skill

This skill implements the **Initialization** part of the Obsidian Nexus workflow. It uses the configuration from the extension settings.

## Commands

### 1. `nexus scout feature <directory_path>`
Performs a surgical, deep dive into a specific feature folder.
- **Deep Investigation**: Use `codebase_investigator` to analyze EVERY line of code in the target `<directory_path>`.
- **Language Detection**: Automatically identify the language (Dart, JS, Python, etc.) to understand syntax.
- **Dependency Tracing**: Identify all project-local imports or requires pointing to other files in the project.
- **Surgical Deep Read**: For every local dependency found, Gemini MUST read the ENTIRE file carefully, ensuring no detail is missed.
- **Vault Export**: Create/Update a dedicated folder in `${settings.vault_path}\${settings.project_name}\Brain\Features/[FeatureName]/` with structured files:
    - `Logic.md`: Business logic, state flows, and core algorithms.
    - `UI.md`: Components, styling, and visual structure (if applicable).
    - `Data.md`: Models, API interactions, and storage logic.

### 2. `nexus scout full`
Performs a high-level overview of the entire project structure.
- **Structure Map**: Map the entire file tree and save it to `${settings.vault_path}\${settings.project_name}\Brain\Structure Map.md`.
- **Package Audit**: Analyze the project's manifest (e.g., `pubspec.yaml`, `package.json`, `requirements.txt`) to explain the purpose of each dependency and save it to `${settings.vault_path}\${settings.project_name}\Brain\Package Audit.md`.
- **Architecture Sync**: Generate/Update `${settings.vault_path}\${settings.project_name}\Brain\Architecture.md` with global routing, state management strategy, and project conventions.

## Instructions
- Use `codebase_investigator` for the initial scan.
- Always provide line-by-line detail for the feature logic in the final output.
- Organize information using the feature-based sub-folder structure in the vault.

## Triggers
- "Scout Feature"
- "Deep Scan"
- "Map Architecture"
- "Initialize Project in Obsidian"

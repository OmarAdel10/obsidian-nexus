---
name: nexus-sync
description: Maintenance Tool. Syncs developer identity, project roadmap, architecture, plans, and session history between Gemini CLI and Obsidian. Use at session start for 'Handshake' and session end for 'Summarize'.
---

# Nexus Sync Skill

This skill implements the **Maintenance** part of the Obsidian Nexus workflow. It uses the configuration from the `obsidian-link` extension settings.

## Workflow

### 1. Identity Handshake (Global)
At the start of ANY session, Gemini MUST read your profile.
- Read `${settings.vault_path}\Identity\Developer Profile.md`

### 2. Session Handshake (Project)
Before starting work on a specific project, Gemini MUST read the roadmap, architecture, active plans, and latest logs.
- **Roadmap**: Read `${settings.vault_path}\Brain\${settings.project_name} Brain.md`.
- **Architecture**: Read `${settings.vault_path}\Brain\Architecture.md`.
- **Active Plans**: Read `${settings.vault_path}\Plans\` to find any active implementation plans for this project.
- **Recent History**: Read the last 5 entries in `${settings.vault_path}\Journal\`.

### 3. Memory Persistence (Session End)
When finishing a session, Gemini MUST summarize the work.
- **Create Daily Note**: Use `write_file` to create a new file in `${settings.vault_path}\Journal\` named `DD-MM-YYYY [Session Name].md`.
- **Apply Template**: Follow the structure in `${settings.vault_path}\Templates\Session Log Template.md`.
- **Update Brain**: Update milestones or state in `${settings.vault_path}\Brain\${settings.project_name} Brain.md`.
- **Update Plans**: Mark completed tasks in the active plan in `${settings.vault_path}\Plans\`.

## Standard Handshake Procedure
When triggered with "handshake":
1. `read_file` Identity/Developer Profile.
2. `read_file` Brain/${settings.project_name} Brain.
3. `read_file` Brain/Architecture.md.
4. `list_directory` Plans to check for current task progress.
5. `list_directory` Journal to find recent sessions.
6. Output: "Handshake Complete. Identity, Brain, and Plans Synchronized for ${settings.project_name}."

## Triggers
- "Handshake"
- "Sync with Obsidian"
- "Who am I?"
- "What's the project status?"
- "Summarize to Obsidian"

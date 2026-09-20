---
name: second-brain-kit
description: Set up a GitHub-backed, Obsidian-compatible Second Brain for humans and AI agents. Use when creating a new Second Brain with Inbox, Sources, Knowledge, Projects, Outputs, and System layers.
user-invocable: true
---

# Second Brain Kit

Build a Second Brain that remains readable as Markdown, works with Obsidian, and can be shared by multiple AI agents through GitHub.

## Setup workflow

GitHub is the minimum required shared storage for this kit. A local Obsidian Vault is optional and can be connected later.

When the user asks to set up a Second Brain:

### Interaction rule

Setup is sequential. **Ask exactly one question at a time.** During setup, ask only questions required to resolve the GitHub repository, its privacy, and direct read/write access. Do not ask about language, Projects, local Vaults, migration, taxonomy, tags, or other optional configuration.

Finish and verify the current step before asking the next required question. Once GitHub is ready, create the standard structure immediately.

1. **Resolve the GitHub repository first.**
   - Ask whether the user already has a GitHub repository for the Second Brain.
   - If yes, ask them to provide the repository URL or identifier and use that repository.
   - If not, the repository name must be chosen by the user. Never silently choose or create a repository name on their behalf.
   - If the current agent can create GitHub repositories directly, ask whether the user wants the agent to create it now or prefers to create it themselves and provide the URL afterward.
   - If the user wants the agent to create it, ask for the repository name and any required repository settings before creating it.
   - If the current agent cannot create repositories directly, state that limitation clearly and ask the user to create the repository and provide its URL when ready. Then ask whether they need concise instructions for creating a GitHub repository.
   - Do not provide beginner GitHub instructions unless the user asks for help.

2. **Verify repository privacy and direct GitHub access before setup.**
   - Check the target repository's visibility before writing Second Brain content.
   - Strongly recommend a **private** repository because a Second Brain may contain personal notes, project context, unpublished writing, and other information that should not be public by default.
   - If the repository is public, warn the user clearly before continuing. Ask whether they want to make it private.
   - If the current agent can change repository visibility directly, only do so after the user explicitly asks or agrees.
   - If the agent cannot change repository visibility directly, provide concise instructions for changing the repository to private when the user wants help.
   - Do not silently change repository visibility.
   - Check whether the current agent can directly read and write the target repository through an available GitHub integration, connector, MCP server, CLI, or authenticated API.
   - Prefer direct authenticated access. Do not default to browser automation for repository setup or normal maintenance.
   - If direct access is unavailable, tell the user what capability is missing and help them connect or authenticate an appropriate GitHub integration before continuing.
   - Do not claim setup is complete until the required files have actually been written to the repository.

3. **Create the Second Brain immediately after GitHub is ready.**

Create the standard structure without asking for initial Projects, language, tags, taxonomy, or other optional preferences:

```text
00 Inbox/
10 Sources/
20 Knowledge/
30 Projects/
40 Outputs/
90 System/
```

4. Copy the templates from this Skill into the target:
   - `templates/AGENTS.md` → `AGENTS.md`
   - `templates/schema.md` → `90 System/schema.md`
   - `templates/workflows.md` → `90 System/workflows.md`
   - `templates/weekly-knowledge-review.md` → `90 System/weekly-knowledge-review.md`
5. Create `90 System/index.md` and `90 System/log.md`.
6. Make a focused initialization commit.
7. Verify that the expected structure and files exist in the target repository.
8. Tell the user setup is complete. Keep the completion message concise and do not automatically start another workflow.

After setup, the user may separately ask to add content, create Projects, connect a local Obsidian Vault, or migrate an existing knowledge base. These are follow-up tasks, not part of the default setup flow.

## Core model

- **Inbox** — captured but not processed.
- **Sources** — normalized records of external material and provenance.
- **Knowledge** — durable synthesis that can be updated over time.
- **Projects** — project-specific context and application of reusable Knowledge.
- **Outputs** — publishable or shareable artifacts.
- **System** — schemas, workflows, maintenance rules, indexes, and logs.

A Source is not Knowledge. Preserve what the source said, then synthesize reusable conclusions into Knowledge.

Prefer updating an existing Knowledge note over creating a near-duplicate.

## Maintenance

Maintenance must be incremental.

For routine reviews, process newly captured or unreviewed Sources and the Knowledge notes they materially affect. Do not re-read the entire Source archive unless the user explicitly asks for a full audit.

After a Source has been considered, mark it reviewed. Preserve links from Sources to Knowledge so synthesized conclusions remain traceable.

Use `templates/weekly-knowledge-review.md` as the default weekly maintenance workflow.

## Guardrails

- Never mass-delete notes without explicit instruction.
- Never silently replace human-authored opinions with AI conclusions.
- Preserve URLs and provenance.
- Keep Markdown readable outside Obsidian.
- Use `[[wikilinks]]` where useful, but do not make Obsidian-specific features mandatory for basic readability.
- Git history is the audit trail; avoid force-push as a normal workflow.

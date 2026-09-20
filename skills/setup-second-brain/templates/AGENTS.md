# AGENTS.md — Second Brain

This repository is the canonical knowledge base and Obsidian-compatible Vault.

All AI agents and human editors should follow these rules.

## Core principles

1. Separate captured material, Sources, synthesized Knowledge, project application, and Outputs.
2. Prefer updating an existing Knowledge note over creating a near-duplicate.
3. Preserve URLs and provenance for externally sourced information.
4. Do not overwrite human-authored opinions with AI conclusions.
5. Keep files readable as plain Markdown.
6. Use `[[wikilinks]]` for useful internal relationships.
7. Git history is the audit trail. Make focused commits.

## Structure

- `00 Inbox/` — unprocessed captures and temporary notes.
- `10 Sources/` — normalized records of external material.
- `20 Knowledge/` — durable, synthesized, reusable knowledge.
- `30 Projects/` — project-specific context and application.
- `40 Outputs/` — publishable or shareable artifacts.
- `90 System/` — schemas, workflows, indexes, logs, and maintenance rules.

## Ingestion

For a new capture:

1. Preserve the original URL or reference.
2. Create or update a Source when the source is worth retaining.
3. Search for related Knowledge.
4. Update existing Knowledge when possible.
5. Create new Knowledge only for a materially distinct concept.
6. Add useful links between Sources, Knowledge, Projects, and Outputs.

Periodic Source-to-Knowledge maintenance follows `90 System/weekly-knowledge-review.md` and should be incremental.

## AI editing

Before editing Knowledge, read the existing note completely. Merge new evidence into the current structure, preserve useful material, and keep uncertainty or disagreements visible.

Do not mass-delete, mass-rename, or create large numbers of tiny notes without a clear need.

## Git

Pull before editing when practical. Commit and push after a coherent change. Never force-push as a normal synchronization mechanism. Preserve both sides of knowledge conflicts until their meaning has been reviewed.

## System

Read these before major maintenance:

- `90 System/schema.md`
- `90 System/workflows.md`
- `90 System/weekly-knowledge-review.md`
- `90 System/index.md`

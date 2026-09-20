# Workflows

## Capture

Capture first, organize later. New material can enter `00 Inbox/` from mobile sharing, browser clipping, AI conversations, or manual notes.

Preserve the original URL/reference and a short note about why it matters when available.

## Source ingestion

For each useful capture:

1. Preserve it as a Source.
2. Search related Knowledge.
3. Update existing Knowledge when possible.
4. Create new Knowledge only for a materially distinct concept.
5. Preserve links between Source and Knowledge.
6. Link relevant Projects without copying reusable Knowledge into them.

One Source can update multiple Knowledge notes. Multiple Sources can support one Knowledge note.

## Project use

Projects consume Knowledge; they do not own reusable Knowledge. Keep implementation-specific decisions in the Project and link shared concepts back to `20 Knowledge/`.

## Outputs

Outputs are products of the knowledge base, not the canonical source for reusable concepts. If writing an Output creates a durable insight, propagate it back into Knowledge.

## Routine maintenance

Routine maintenance may process Inbox items, normalize Sources, update recently affected Knowledge, repair obvious links, and remove duplication.

Do not reorganize the entire Vault during normal maintenance.

## Git synchronization

Before a local editing session when practical:

```bash
git pull --rebase
```

After meaningful edits:

```bash
git add -A
git commit -m "<scope>: <change>"
git push
```

Avoid force-push as a normal synchronization mechanism.

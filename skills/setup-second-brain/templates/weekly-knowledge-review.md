# Weekly Knowledge Review

The goal is incremental maintenance: turn recent Sources into durable Knowledge without re-reading the entire archive every week.

## Review scope

Start with:

- Sources captured since the previous review.
- Sources with `reviewed: false`.
- Knowledge notes materially affected by those Sources.
- Obvious duplication, contradiction, or outdated conclusions exposed by the new material.

Previously reviewed Sources may be revisited when a topic changes materially.

## Workflow

### 1. Review new Sources

Group recent Sources by topic and identify new information, repetition, disagreement, outdated material, and material that is interesting but not yet reusable.

### 2. Decide whether Knowledge should change

Update Knowledge when the new material creates a reusable conclusion, changes an existing conclusion, exposes a useful disagreement, or is about to be applied to a Project or Output.

Do not create Knowledge merely because a Source exists.

### 3. Update Knowledge

Search for an existing Knowledge note first. Read it completely, merge the new evidence, preserve uncertainty, add Source references, and update its date.

Create a new Knowledge note only when the concept is materially distinct.

### 4. Mark Sources reviewed

After a Source has been considered:

```yaml
reviewed: true
```

When it materially contributes to Knowledge:

```yaml
knowledge:
  - "[[Relevant Knowledge Note]]"
```

### 5. Keep history, improve synthesis

Prefer consolidation over deleting Sources. Sources preserve provenance; Knowledge should represent the current useful synthesis.

A normal review should make a small number of meaningful changes rather than restructure the whole Vault.

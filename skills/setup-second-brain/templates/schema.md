# Note Schema

## Common fields

```yaml
---
type: knowledge
created: YYYY-MM-DD
updated: YYYY-MM-DD
status: active
tags: []
projects: []
---
```

Primary `type` values: `inbox`, `source`, `knowledge`, `project`, `output`, `system`.

## Source

```yaml
---
type: source
source_type: article
source_url:
source_title:
author:
published:
captured: YYYY-MM-DD
status: active
reviewed: false
tags: []
projects: []
knowledge: []
---
```

`captured` identifies recent material for incremental maintenance.

`reviewed: false` means the Source has not yet been considered for synthesis. After review, set it to `true`. Reviewed Sources may still be revisited when new evidence materially changes a topic.

`knowledge` lists Knowledge notes that materially synthesize or use the Source.

Useful Source lifecycle states include `active`, `deprecated`, `superseded`, and `archived`.

## Knowledge

Knowledge should synthesize reusable conclusions rather than concatenate Source summaries.

```yaml
---
type: knowledge
created: YYYY-MM-DD
updated: YYYY-MM-DD
status: active
tags: []
projects: []
---
```

## Project

```yaml
---
type: project
project:
created: YYYY-MM-DD
updated: YYYY-MM-DD
status: active
tags: []
---
```

## Output

```yaml
---
type: output
output_type:
title:
created: YYYY-MM-DD
updated: YYYY-MM-DD
status: draft
tags: []
projects: []
---
```

---
id: decision-2026-05-14-atomic-node-going-forward
type: decision
date: 2026-05-14
summary: New decisions, inferences, contexts, tests authored as individual frontmatter-typed .md files, not appended to rolling logs.
authored_by: dailen
supports: []
derived_from: [inference-2026-05-13-infinite-brain-pattern]
contradicts: []
related_to: [decision-2026-05-14-retrieval-contract-layer-0]
---

## Context

Before 2026-05-14, every decision landed in one rolling `Decisions Log.md` file. The agent had to read the entire file every time it needed context on any single decision. At 50+ decisions the file was over 30KB, costing significant tokens per session for what was usually a single-decision lookup.

## Decision

Adopt atomic-node format for all new captures starting 2026-05-14. Atom types: `decision`, `inference`, `context`, `test`. Edge types: `supports`, `derived_from`, `contradicts`, `related_to`. Format spec at `templates/decision-node.md` and the other three atom templates.

Legacy `Decisions Log.md` becomes a rolling index that links to atomic nodes, not the source of truth.

## Why this over alternatives

Rewriting the legacy corpus to atomic format = months of work. Continuing the rolling-log pattern = preserves a known token-cost waste. Atomic-forward plus index-legacy = minimum-viable transition that compounds going forward without retroactive cost.

## Status

`locked` — all new captures atomic-typed since 2026-05-14.

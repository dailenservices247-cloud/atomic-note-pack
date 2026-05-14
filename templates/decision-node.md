---
id: decision-YYYY-MM-DD-<slug>
type: decision
date: YYYY-MM-DD
summary: <one sentence, max 140 chars, what you decided>
authored_by: <your-name>
supports: []
derived_from: []
contradicts: []
related_to: []
---

## Context

What was true before this decision. The setup. What forced the choice.

## Decision

The substance. One claim per node. State the decision in present tense, as a settled outcome.

## Why this over alternatives

Briefly name the alternative paths you considered. Why you rejected each. Future-you needs this when context changes and the decision needs revisiting.

## Status

`locked` | `pilot` | `draft` | `superseded`

If `superseded`, link the replacement node:
```yaml
superseded_by: decision-YYYY-MM-DD-<replacement-slug>
```

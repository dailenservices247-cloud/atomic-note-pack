---
id: test-YYYY-MM-DD-<slug>
type: test
date: YYYY-MM-DD
summary: <one sentence, max 140 chars, what you tested and the headline result>
authored_by: <your-name>
supports: []
derived_from: []
contradicts: []
related_to: []
---

## Hypothesis

What you expected to be true before you ran the test.

## Test

How you tested. Tool, sample size, time window, controls. Enough detail that someone else (or future-you) could repeat the test.

## Result

What happened. Numbers, observations, screenshots if relevant. State the result against the hypothesis explicitly: confirmed / contradicted / inconclusive.

## What this changes

What decision or inference this result updates. Link the affected nodes via `supports` or `contradicts` in frontmatter.

## Status

`passed` | `failed` | `inconclusive` | `superseded`

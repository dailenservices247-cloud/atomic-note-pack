---
project: <project-name>
agent_purpose: <one sentence on what the agent does for this project>
authored_by: <your-name>
date: YYYY-MM-DD
status: draft | piloted | locked | superseded
---

## What the agent needs to know

| Fact type | Shape | Refresh cadence |
|---|---|---|
| <e.g. brand voice register> | <e.g. markdown file at path X> | <e.g. weekly> |
| <e.g. active project state> | <e.g. file at app/page.tsx> | <e.g. per session> |
| ... | ... | ... |

## Retrieval triggers

| When | What gets pulled | How filtered |
|---|---|---|
| <e.g. user asks for copy generation> | <e.g. canon/voice/*.md> | <e.g. dissect-then-generate 2-prompt sequence> |
| <e.g. UI change request> | <e.g. design tokens + brand register> | <e.g. anti-pattern check on generated CSS> |
| ... | ... | ... |

## Token budget per turn

- Max context loaded: <e.g. 12000 tokens>
- Max retrieval calls: <e.g. 4 per turn>
- Fallback when over: <e.g. summary-only mode + user re-prompt>

## Anti-patterns banned

Explicit list of rediscovery patterns the agent must refuse:

- <e.g. re-reading handoff.md from scratch every turn>
- <e.g. re-asking questions answered in CLAUDE.md>
- <e.g. searching for the offer catalog when it lives in this contract>
- <e.g. loading entire canon directory at once>

## Status

`draft` (under construction) | `piloted` (running, under observation) | `locked` (stable, no recent changes) | `superseded` (replaced by a newer contract)

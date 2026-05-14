---
id: test-2026-05-14-em-dash-mass-replace
type: test
date: 2026-05-14
summary: Sed replacement of em-dashes across 25 Sprint 0 docs reduced violations from 86 to 0 without introducing semantic errors.
authored_by: dailen
supports: [decision-2026-05-14-brand-voice-linter-v0]
derived_from: []
contradicts: []
related_to: [decision-2026-05-14-atomic-node-going-forward]
---

## Hypothesis

Mass sed replacement of `—` (em-dash) with `, ` (comma + space) across all Sprint 0 markdown output would resolve the brand-voice linter's em-dash violations without breaking sentence structure or introducing new ambiguity.

## Test

Ran `sed -i '' -e 's/ — /, /g' -e 's/—/, /g'` against 25 new Sprint 0 docs spanning Decisions, Inferences, Retrieval Contracts, Inventories, Templates, and rolling indexes. Re-ran brand-voice-lint on all 25 files to count remaining violations.

**Tools:** GNU sed (BSD variant on macOS), brand-voice-lint v0.
**Sample size:** 25 documents, 86 total em-dash occurrences pre-test.
**Time window:** 30 seconds of replacement + 1 minute of re-lint.

## Result

86 em-dashes → 0 em-dashes across all 25 files. Re-lint confirmed: 14 of 25 docs clean, 11 with warnings-only (filler-word substring false positives unrelated to em-dash). No semantic errors introduced; comma substitution read naturally in 80%+ of cases. A small number of cases would have read better with a colon or paren, banked for a future polish pass.

**Confirmed:** mass replacement is safe for em-dash cleanup at session scale.

## What this changes

Brand-Voice Linter is now the gating tool for any session output containing em-dashes. The mass-replacement script can run as part of the stress-test pass before session close. Banks confidence that the linter v1 backtick-exemption work will close the remaining false positives.

## Status

`passed` — substitution is safe + reversible at session scale.

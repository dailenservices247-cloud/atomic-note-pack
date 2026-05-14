---
project: sds-website
agent_purpose: Build and iterate the Synapse Dynamics Segmented public site, brand-v3 register, Nox mascot integration, conversion funnel from lead magnet to retainer.
authored_by: dailen
date: 2026-05-14
status: piloted
---

## What the agent needs to know

| Fact type | Shape | Refresh cadence |
|---|---|---|
| Brand v3 visual tokens | `lib/design/brand-v3-tokens.ts` (palette + Bricolage + Geist + JetBrains Mono) | On any token change |
| Brand voice taste profile | `~/.claude/canon/voice/` plus banned-words register | Weekly review |
| Brand-Voice Linter rule pack | Hardcoded in `~/.local/bin/brand-voice-lint` | On rule pack update |
| Mascot Nox lock state | `Decisions/decision-2026-05-08-mascot-lock.md` + `public/brand-v3/*.png` | Locked; only delta on Phase 2-6 work |
| Offerings catalog + funnel | `Inferences/inference-2026-05-14-sds-os-v1-catalog.md` | Per-launch update |
| Active page state | `app/(brand-v3)/v1-garden/page.tsx`, `components/brand-v3/nox/*.tsx` | Per session |
| Current handoff | `~/.claude/handoffs/synapse.md` | Per session |

## Retrieval triggers

| When | What gets pulled | How filtered |
|---|---|---|
| Copy generation (hero, body, CTA, microcopy) | Voice canon + banned-words list + Doctrine Injection sources | 2-prompt dissect-then-generate sequence |
| Visual change (component, layout, motion) | Brand v3 tokens + Impeccable register check | Reject pure-black/gray, Inter/Roboto, bounce easing, gradient text, side-stripe borders |
| Mascot work (Nox positioning, motion, segmentation) | Mascot lock decision + 7 PNG artifacts + Phase 2 brief (banked) | Lock state takes precedence over any iteration request |
| Routing / page structure changes | Current page state + funnel arch | Per-page conversion target tagged |
| Pricing / offering copy | Pricing tier map + offering catalog | Tier-specific framing per upper-tier-only rule |

## Token budget per turn

- Max context loaded: 12,000 tokens
- Max retrieval calls: 4 per turn
- Fallback when over: summary-only mode plus explicit user re-prompt for the dropped slice

## Anti-patterns banned

- Re-reading `~/.claude/handoffs/synapse.md` from scratch every turn (load once, reference, update at end)
- Re-asking known brand decisions (palette, type, mascot lock), they're locked
- Searching `lib/content/services.ts` for the catalog, it's in this contract via the inference link
- Loading entire `~/.claude/canon/` directory at once, use Doctrine Injection 2-prompt sequence with 2-4 sources max
- Generating copy without first running it through banned-words check
- Re-discovering Brand v3 anti-patterns mid-session, they're locked in `~/.claude/CLAUDE.md`

## Status

`piloted`, drafted 2026-05-14, in use across first 5 sessions. Will promote to `locked` after 30 days of stable use.

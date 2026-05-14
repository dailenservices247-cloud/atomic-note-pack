# Atomic Note Template Pack

Five Obsidian-ready markdown templates that turn a sprawling vault into a graph-native memory the AI in your stack can scan, follow, and act on.

Built by [Synapse Dynamics Segmented](https://github.com/dailenservices247-cloud). Free under MIT, or pay $19 to support the work. Either way, all content here is identical.

[Pay $19, support the work](https://buy.stripe.com/REPLACE_WITH_PAYMENT_LINK)
&nbsp;&nbsp;|&nbsp;&nbsp;
[Just take it](https://github.com/dailenservices247-cloud/atomic-note-pack/archive/refs/heads/main.zip)

## What you get

| Template | Atom type | Use for |
|---|---|---|
| `decision-node.md` | decision | A locked choice plus alternatives considered |
| `inference-node.md` | inference | A claim or pattern derived from sources |
| `context-node.md` | context | A snapshot of state at a moment in time |
| `test-node.md` | test | A validation, eval, or experiment with results |
| `retrieval-contract.md` | retrieval contract | What an agent needs to know, in what shape, with what triggers, before any infrastructure pick |

Plus one filled-in example per template under `examples/`.

## Why atomic, why typed

The default vault structure (one rolling `decisions-log.md`, one `lessons-learned.md`, one `meeting-notes.md`) forces any AI agent to read the entire file every time it needs context. At scale, that wastes 85% of agent compute on rediscovering things the system already wrote down (the number is from Pinecone's 2026 analysis of agent rediscovery patterns).

The atomic-node format inverts this. Each decision, each inference, each context snapshot, each test result lives in its own short markdown file with a one-sentence summary at the top. Agents scan the summaries cheaply, follow typed edges (`supports`, `derived_from`, `contradicts`, `related_to`) only when they need detail.

Four atom types is the minimum that maps onto how knowledge actually accumulates in a working business:

- **Decision**, you locked a choice; the alternatives matter for future reversibility
- **Inference**, you pulled a pattern from one or more sources; the source chain matters for credibility
- **Context**, you captured a moment; later you'll need to know what was true when
- **Test**, you ran an experiment or eval; the result matters more than your hypothesis

Four edge types is the minimum that lets the graph compound:

- `supports`, this node strengthens that one
- `derived_from`, this node came from that one
- `contradicts`, this node disagrees with that one
- `related_to`, same depth, no strict dependency

Resist adding new edge types until a pattern repeats 3+ times. The discipline is the point.

## How to use

### Obsidian setup (recommended)

1. Drop the `templates/` folder into your Obsidian vault's `_templates/` directory
2. Enable the Templater plugin (or use core Templates)
3. Create new notes by invoking the template, fill in the frontmatter, write the body
4. Each atom gets its own file in `Decisions/`, `Inferences/`, `Contexts/`, `Tests/`, `Retrieval Contracts/`

Obsidian's graph view will surface the edges automatically once frontmatter is populated. Dataview / Datacore plugins let you query across atom types.

### Filesystem setup (any markdown editor)

The templates are plain markdown with YAML frontmatter. They work in any editor. The folder structure is:

```
vault/
├── Decisions/
│   └── decision-YYYY-MM-DD-<slug>.md
├── Inferences/
│   └── inference-YYYY-MM-DD-<slug>.md
├── Contexts/
│   └── context-YYYY-MM-DD-<slug>.md
├── Tests/
│   └── test-YYYY-MM-DD-<slug>.md
└── Retrieval Contracts/
    └── <project>.md
```

Rolling index files (`Decisions Log.md`, `Lessons Learned.md`) link to the atomic nodes but are NOT the source of truth.

### Notion setup

Each template's frontmatter maps to Notion database properties one-to-one. Create a Notion database per atom type, set the columns to match the YAML keys, paste the body into the page content. The graph view in Notion mirrors the Obsidian graph.

### Cursor / Claude Code / Codex setup

Your agent reads CLAUDE.md / AGENTS.md / similar root files. Add this line:

```
Memory format: atomic-node going forward. New decisions / inferences / contexts /
tests get authored as individual frontmatter-typed .md files under <vault>/<type>/.
Format spec: templates/decision-node.md (and the others). Edge types are limited
to supports / derived_from / contradicts / related_to. Resist adding new edge types.
```

The agent will start producing atomic-node output instead of rolling-log paragraphs.

## What this pack is NOT

- Not a productivity system. The templates store; they don't process.
- Not a replacement for project management. Atomic nodes complement Linear / Asana / Notion; they don't replace them.
- Not opinionated about cadence. Some people atomize on capture; some atomize on review. Both work.
- Not a closed system. Add atom types if your work needs them. The four here are a load-bearing minimum.

## Provenance

This format derives from:

- AI Impact's "Infinite Brain" concept (2025), atomic typed nodes with cheap scan layer
- Nate B Jones' memory-wars analysis (2026), retrieval contracts before infrastructure
- Synapse Dynamics Segmented's own production discipline since 2026-05-14, when the format was locked in `~/.claude/CLAUDE.md` as the going-forward memory format

## License

MIT. Use the templates in your own work, your clients' work, anywhere. Attribution appreciated but not required. The Synapse Dynamics Segmented branding in the examples is illustrative; replace with yours.

## Support the work

If this pack saves you time, or your AI agent stops rediscovering things you already wrote down, consider [paying $19](https://buy.stripe.com/REPLACE_WITH_PAYMENT_LINK). It funds the next round of canon and template work.

## Author

Built by [Dailen Huntley](https://github.com/dailenservices247-cloud) at Synapse Dynamics Segmented. Questions, contributions, or feedback via [issues](https://github.com/dailenservices247-cloud/atomic-note-pack/issues).

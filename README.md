# persona-universal- for exploration purpose

> Runs an AI readiness analysis on your team's personas.
> Tells you what's missing, where AI will create problems, and what to ask users before building anything.
> Works with any AI model. Every insight cites its source — nothing is made up.

---

## What it does

Takes your existing persona documents and evaluates them against an 11-attribute AI-Enhanced Persona framework. For each persona it tells you:

- Which AI-design attributes are covered, partial, or missing
- What human agency model (HITL / HOTL / HIC) applies per task
- Where AI creates value and risk across the user journey
- What to ask users before scoping any AI feature
- What to build into the agent spec sheet before deployment

Outputs a self-contained HTML dashboard, viewable in any browser on a local server.

---

## How to use it

### Claude (Claude Code CLI)

Save the skill file to your commands folder and invoke it:

```bash
# Save to your Claude commands folder
cp persona-universal.md ~/.claude/commands/persona-universal.md

# Run it
/persona-universal
```

### ChatGPT / GPT-4

Paste the full contents of `persona-universal.md` as your first message or as the system prompt. Then share your persona materials in the next message.

### Gemini or other models

Same as above — paste as system prompt, then share materials.

### Sharing with another team

Send them this README and the `persona-universal.md` file. They drop it into their AI tool and run it against their own persona folder.

---

## What you need to have ready

| Input | Format | Required? |
|-------|--------|-----------|
| Persona documents | `.md`, `.txt`, `.pdf`, or pasted text | Yes |
| Product or service description | Plain text, URL (copy-paste relevant sections), or doc | Yes |
| AI capabilities you're planning or building | Plain text list | Yes |
| Existing user research or survey findings | Any format, with source labels | Optional but recommended |
| Market research or benchmarks | Stats with source name and date | Optional |
| Compliance or privacy constraints | Plain text | Optional |
| Internal AI governance policy | Plain text or file | Optional |

Unsourced statistics are not used in the output. If no benchmark is provided, a placeholder is inserted instead.

---

## What you get

### Per persona
- Coverage score (X / 11 attributes)
- Most critical gap with direct quote from the persona document
- Human agency model per task (HITL / HOTL / HIC)
- Automation comfort bar chart
- Top Jobs-to-Agents tasks with delegability rating
- Journey map: highest AI value stage, highest AI risk stage, trust cliff
- 8 UX research questions, each linked to a specific gap

### Across all personas
- Shared gaps (missing from every persona — need a batch fix)
- Recommended research order
- Data governance risk summary
- Top 3 priority actions for the team

### Output file
Self-contained HTML dashboard — no external dependencies, works offline.
Launched via: `python3 -m http.server 8765`

---

## The 11 AI-Enhanced Persona Attributes

These are what the skill checks against each persona document.

| # | Attribute | What it drives |
|---|-----------|---------------|
| 1 | Bio & Demographics | AI communication style and system access scope |
| 2 | Goals | Which goals AI accelerates vs. threatens |
| 3 | Pain Points | Problems AI could fix or make worse |
| 4 | Motivations (scored) | Whether this persona will accept or override AI recommendations |
| 5 | Software & Devices | Where the AI lives and what it can read or write |
| 6 | **Ethical Guidelines** | **Every agent boundary decision — HITL / HOTL / HIC per task** |
| 7 | AI Fluency | Language, explanation depth, error communication |
| 8 | Privacy & Data Need | What the AI can access on this persona's behalf |
| 9 | Failure Tolerance | Error recovery design, undo controls, confidence indicators |
| 10 | Automation Comfort Zones | Which tasks agents can execute vs. which need human initiation |
| 11 | Jobs-to-Agents Tasks | Design priorities (Wants AI) vs. lower urgency (Accepts AI) |

---

## Human Agency Models

Assigned per task domain — most personas need more than one.

| Model | Meaning | Use when |
|-------|---------|---------|
| **HITL** — Human in the Loop | Human approves before AI acts | High-stakes, legally binding, financial, compliance, first-time behaviours |
| **HOTL** — Human on the Loop | AI acts; human monitors and can step in | Routine, reversible, high-volume, well-understood tasks |
| **HIC** — Human in Command | Human sets rules; AI runs within them | A/B testing, fraud monitoring, sandboxed tasks, validated behaviour |

---

## Universal Persona Archetypes

When no archetype is defined, the skill maps each persona to the closest match below. Deviations from the archetype are the most valuable signal.

| Archetype | Core concern about AI | Default model |
|-----------|----------------------|---------------|
| Operational Executor | Will AI make my job harder or replace me? | HITL on exceptions / HOTL on routine |
| Knowledge Broker | Will AI recommendations be accurate enough to stake my credibility on? | HOTL |
| Creative Producer | Will AI output match our quality and brand standards? | HOTL for drafts / HITL for publish |
| Approver / Decision Authority | Can I understand why AI recommended this, and am I liable if I follow it? | HITL |
| Systems Custodian | Who's responsible when something breaks? | HIC / HITL on production changes |
| Relationship Manager | Will AI undermine the trust I've built with my customers? | HITL on customer-facing / HIC on background |
| Strategic Leader | Can I trust the data I'm making decisions with? | HIC / HITL on financial commitments |

---

## Traceability rule

Every insight in the output is labelled as one of:

- `[From: filename — "direct quote"]` — sourced from your persona or product documents
- `[From: research — "source name, date"]` — sourced from materials you provided
- `[Framework principle — not from your materials]` — derived from the skill framework itself

Nothing appears without a label. No statistics are generated without a source you provided.

---

## Minimum viable persona

The skill runs on partial information. Missing fields are flagged in the output.

| Field | Required? | If missing |
|-------|-----------|-----------|
| Name / Role | Yes | Skill pauses and asks |
| Goals (at least 2) | Yes | Gap section will be limited |
| Pain points (at least 1) | Yes | Journey map risk section will be limited |
| Tools used | Recommended | Tool recommendations will be omitted |
| Defining quote | Optional | Trust and failure analysis less specific |
| Jobs to be done | Recommended | Jobs-to-Agents uses archetype defaults only |

---

## After the analysis — next steps

The skill covers the **Plan** phase of agent development. For the full lifecycle:

| Phase | What to do next |
|-------|----------------|
| Build & Integrate | Complete an agent spec sheet per agent scoped in the analysis |
| Deploy & Monitor | Agree metrics before deployment — not after |
| Optimize & Maintain | Version every config change and set up a feedback channel |
| Retire & Replace | Define retirement triggers before the agent ships |

See the `agent-governance/` folder for templates covering all four phases.

---

## Adapting for a new industry

Replace the 7 archetypes in the skill's Step 2 with ones relevant to your domain.
Everything else (11 attributes, agency models, journey map, research questions, dashboard) works as-is.

---

*persona-universal — version 1.2 — August 2026*
*Works with any LLM. Any industry. Any persona format.*
*Every insight cites its source.*

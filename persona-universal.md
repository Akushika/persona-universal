# persona-universal

## What this skill does

Runs an AI readiness analysis on your team's personas. Tells you what's missing, where AI will create problems, and what to ask users before building anything.

Works with any AI model. Outputs an HTML dashboard you can view in a browser. Every insight links back to something you provided — nothing is made up.

---

## One rule that applies throughout

> Every insight, stat, or recommendation must trace back to:
> - Something in your persona documents (quoted directly)
> - Something in the product or research materials you share
> - A principle from this framework (labelled as such)
>
> If it can't be traced, it won't appear.
> Labels used: `[From: filename — "quote"]` and `[Framework principle — not from your materials]`

---

## Step 0 — Setup Questions

Answer these before analysis starts. Required questions are marked. Optional ones add depth but aren't blocking.

---

### A — Your team and the problem

**A1 — Required**
What team are you on, and what do you do?
*e.g. "UX Research for a B2B procurement tool" / "Customer Success, financial services"*

**A2 — Required**
What product or service are these personas for? What does it do, who uses it, and where are you with AI right now?
*e.g. "We run a procurement platform for manufacturers. We're starting to scope AI-assisted approvals."*

**A3 — Required**
What's the main question you need this analysis to answer?
*e.g. "Which personas should own the approval step in our AI workflow?" / "Where will AI break trust with our users?"*

**A4 — Optional**
Who will read this output?
Pick any: `UX / Design` `Product` `Engineering` `Data / AI` `Leadership` `Legal / Compliance`

---

### B — Your personas

**B1 — Required**
How do you want to share your personas? Pick one:

- **Folder path** — share the path (e.g. `/Users/yourname/personas/`). Supports `.md`, `.txt`, `.pdf`.
- **Paste** — copy persona content directly into the chat. Include at minimum: role, goals, pain points, tools used.
- **Both** — folder path plus any extras pasted in.

**B2 — Required**
How many personas are you sharing?
If more than 5, say which 3–5 matter most for AI right now and why.

**B3 — Optional**
Any personas to skip?
*e.g. outdated ones, or consumer personas if your AI work is B2B-only*

---

### C — Product and domain information

**C1 — Required**
Share anything that should ground the analysis. Use whatever format you have.

- **Website URL** — paste it; you'll be asked to copy the relevant sections
- **Product docs** — paste text or share a file path
- **Feature list or roadmap** — plain text or bullet list is fine
- **Nothing available** — analysis will use persona content and framework only, labelled clearly

**C2 — Required**
What AI capabilities are you planning, building, or have already shipped?
Be specific.
*e.g. "AI email drafts for our CS team" / "Conversational search on our catalogue" / "Automated purchase approvals"*
If nothing yet: what's being discussed?

**C3 — Optional**
Any AI tools or platforms already in use or being evaluated?
*e.g. OpenAI API, Microsoft Copilot, an internal model, a SaaS product with embedded AI*

---

### D — Research and insights you already have

**D1 — Required**
Do you have any existing user research, survey data, usability findings, or analytics you'd like to factor in?

Share in any format:
- Paste findings or quotes directly
- Share a file path to research documents
- Paste stats with their source name and date

These will be used to validate or challenge what the persona documents say.
If you have nothing: say so — the analysis will flag where user research is still needed.

**D2 — Optional**
Do you have any market research, industry benchmarks, or competitor analysis relevant to your AI work?
Paste the key numbers with their source.
*e.g. "Our NPS survey showed 62% of users don't trust automated approvals — internal survey, Q2 2026"*
Unsourced stats will not be used in the output.

**D3 — Optional**
Has your team run any previous AI experiments, pilots, or A/B tests?
What did you learn?
This helps avoid repeating gaps already discovered.

---

### E — Constraints

**E1 — Required**
Any legal, compliance, or privacy rules that affect what AI can do in your product?
*e.g. GDPR Article 22 (no fully automated decisions affecting users), HIPAA, financial advice regulations, internal AI policy*
If none known: say "none identified" — this gets flagged as a gap.

**E2 — Optional**
Does your organisation have an AI ethics or governance policy?
If yes: what can and can't agents do without human approval?
If no: flagged as a structural gap with a suggested fix.

**E3 — Optional**
What's the worst thing that could happen if AI makes a wrong call for one of your personas?
*e.g. "A bot places a duplicate $50K order" / "Wrong medical dosage in a recommendation"*
This calibrates how strictly each persona's failure tolerance is scored.

---

### F — Output preferences

**F1 — Required**
What do you want at the end?
- `Dashboard only` — HTML file, opens in browser
- `Dashboard + written report` — HTML plus a markdown summary
- `Dashboard + slide content` — HTML plus bullet points ready for a presentation

**F2 — Optional**
Any attributes you want to focus on?
Default: all 11 are checked. To narrow down, name 3–5 most relevant to your current work.
*e.g. "Focus on Ethical Guidelines, AI Fluency, and Failure Tolerance — we're designing our first agent"*

**F3 — Optional**
Should the journey map cover the full user journey, or specific stages only?
Default: full journey. To narrow: name the stages where your AI will operate.

---

## Step 1 — Confirm what was received

Before starting analysis, list:
1. All personas received — name and role as identified
2. All product and domain materials — with their labels
3. All research and insight materials — with source labels
4. Any personas that look incomplete (missing goals, pain points, or tools)
5. Any stats or claims in the materials that have no source — these will be excluded
6. The AI capabilities list from C2

Ask the user to confirm this list before moving on.

---

## Step 2 — Match each persona to an archetype

Find the closest match from the list below. Note where the real persona differs from the archetype — those differences are usually the most useful signal.

### The 7 archetypes

**1. Operational Executor**
Does high-volume, process-driven work. Most at risk of AI replacing tasks.
Core concern: *will AI make my job harder or make me redundant?*
Roles: data entry, order processing, customer service, fulfilment, scheduling
Default AI model: HITL on exceptions / HOTL on routine tasks

**2. Knowledge Broker**
Pulls information from multiple sources to advise others or make recommendations. Most likely to be augmented by AI.
Core concern: *will AI recommendations be accurate enough that I can put my name on them?*
Roles: analyst, consultant, category manager, sales rep, support specialist
Default AI model: HOTL — AI surfaces, human interprets

**3. Creative Producer**
Makes original content, designs, or strategy. Most exposed to AI co-creation.
Core concern: *will AI output match our quality and brand standards?*
Roles: content creator, designer, marketer, copywriter, product designer
Default AI model: HOTL for drafts / HITL for publish

**4. Approver / Decision Authority**
Has final say on high-stakes or policy-bound decisions. Most exposed to AI escalation and recommendation systems.
Core concern: *can I understand why AI recommended this, and am I liable if I follow it?*
Roles: manager, executive, compliance, legal, finance authority
Default AI model: HITL — AI presents, human decides

**5. Systems Custodian**
Owns the infrastructure, data pipelines, or platform setup. Most exposed to AI governance.
Core concern: *who's responsible when something breaks?*
Roles: IT admin, platform engineer, data engineer, DevOps, system architect
Default AI model: HIC — sets guardrails / HITL on production changes

**6. Relationship Manager**
Manages long-term, trust-based relationships where individual judgment matters. Highest tension with AI standardisation.
Core concern: *will AI undermine the trust I've built with my customers or accounts?*
Roles: account manager, enterprise sales, customer success, partner manager
Default AI model: HITL on all customer-facing outputs / HIC on background work

**7. Strategic Leader**
Sets direction and is accountable for outcomes. Exposed to AI through reporting and forecasting.
Core concern: *can I trust the data I'm making decisions with?*
Roles: VP, Director, C-suite, Head of, General Manager
Default AI model: HIC — sets strategy / HITL on financial or legal commitments

---

## Step 3 — Gap analysis (11 attributes)

Check each persona against all 11 attributes. Use only what's in the persona document. Don't fill in gaps from job titles or assumptions.

Score each attribute:
- ✅ **Covered** — specific enough to make an AI design decision
- ⚠️ **Partial** — mentioned but not detailed enough
- ❌ **Missing** — not in the document at all

Priority:
- **High** — gap blocks agent boundary design, governance, accountability, failure recovery, or compliance
- **Medium** — gap affects communication design, onboarding, or trust-building
- **Low** — useful but not blocking any immediate decision

### The 11 attributes

| # | Attribute | What to look for | Why it matters for AI design |
|---|-----------|-----------------|------------------------------|
| 1 | **Bio & Demographics** | Work environment, experience, tools context, where they sit in decisions | Sets the AI's communication style and access boundaries |
| 2 | **Goals** | What they're trying to achieve, regardless of who or what does the work | Shows which goals AI accelerates vs. which ones it threatens |
| 3 | **Pain Points** | Current friction — including frustration with AI errors, over-automation, or bad data | Surfaces problems AI could fix or make worse |
| 4 | **Motivations (scored)** | What drives behaviour: efficiency, control, trust, speed, accuracy | Predicts whether they'll accept or override AI recommendations |
| 5 | **Software & Devices** | Tools, integrations, data systems; mobile vs. desktop | Defines what the AI can read, write, and where it lives |
| 6 | **Ethical Guidelines** | HITL/HOTL/HIC per task; AI fluency; privacy stance; transparency needs | The most important attribute — drives every agent boundary decision |
| 7 | **AI Fluency** | Basic (just tell me the outcome) / Business (I understand the logic) / Technical (I can evaluate models) / Expert (I build AI) | Determines language, explanation depth, and how errors are communicated |
| 8 | **Privacy & Data Need** | What data they create, share, and protect | Controls what the AI can access on their behalf |
| 9 | **Failure Tolerance** | What they do when AI is wrong: stop using it / try again / investigate | Shapes error recovery, undo controls, and confidence indicators |
| 10 | **Automation Comfort Zones** | From "never automate this" to "AI can run this fully" | Sets which tasks agents can execute vs. which need human initiation |
| 11 | **Jobs-to-Agents Tasks** | Tasks they want AI to do vs. tasks they'd just tolerate being automated | Separates design priorities from lower-urgency features |

**Output per persona:**

| Attribute | Status | Quote from persona doc | What's missing | Which capability is affected | Priority |
|-----------|--------|------------------------|----------------|------------------------------|----------|
| [name] | ✅/⚠️/❌ | [quote or "Not present"] | [gap] | [feature or tool] | H/M/L |

**Coverage score:** X / 11

---

## Step 4 — Human agency model per persona

Assign HITL / HOTL / HIC for each task area. Most personas need more than one model.

| Model | What it means | Use it when |
|-------|--------------|-------------|
| **HITL** — Human in the Loop | Human approves before AI acts | High-stakes, legally binding, financial, first-time behaviours, compliance |
| **HOTL** — Human on the Loop | AI acts; human watches and can step in | Routine, reversible, high-volume, well-understood tasks |
| **HIC** — Human in Command | Human sets the rules; AI runs within them | A/B testing, fraud monitoring, sandboxed tasks, validated agent behaviour |

**Output per persona:**

| Task area | Model | Why (cite persona source) | Risk if this is wrong |
|-----------|-------|--------------------------|----------------------|
| [area] | HITL/HOTL/HIC | [quote] | [failure mode] |

Flag immediately if:
- A task is compliance-sensitive but no HITL is assigned
- AI Fluency is Basic but HOTL or HIC is recommended (design mitigation needed)
- A task has no recoverable failure mode under automation

---

## Step 5 — Journey map overlay

Plot each persona's journey and mark where AI creates value and where it creates risk.

If the user hasn't provided a journey map, build one from the persona's jobs and pain points. Label inferred cells as `[Framework inference]`.

### Journey stages (adapt names to fit the user's domain)

| Stage | What the persona wants here | Current pain | AI opportunity | AI risk | Agency model |
|-------|-----------------------------|-------------|----------------|---------|--------------|
| Awareness / Discovery | | | | | |
| Evaluation / Research | | | | | |
| Decision / Approval | | | | | |
| Onboarding / Setup | | | | | |
| Daily Use | | | | | |
| Monitoring / Review | | | | | |
| Support / Recovery | | | | | |

Rules:
- Only fill cells with evidence from user materials
- The AI risk column is mandatory — every opportunity has a risk
- The AI risk column is mandatory — every opportunity has a risk

For each persona, surface:
1. **Highest AI value stage** — where AI most reduces friction (cite the pain point)
2. **Highest AI risk stage** — where an AI error has the worst consequence
3. **Trust cliff** — the point where one wrong AI decision would cause this persona to stop using the tool entirely

---

## Step 6 — Research questions

Generate 8 questions per persona. Each must link to a specific gap from Step 3 or a risk from Step 5.

| # | Question | Method | Targets | Why this matters |
|---|----------|--------|---------|-----------------|
| 1 | [question] | Discovery call / Usability test / Survey / Diary study / Support ticket review | [attribute] | [what AI design decision this unlocks] |

Cover these themes where gaps exist:
- **Trust & autonomy** — where does this persona draw the line?
- **Data & privacy** — what are they protective of?
- **Failure & recovery** — what do they do when AI gets it wrong?
- **Task delegation** — what do they actually want AI to handle?
- **Interaction style** — conversational or command-based? How much explanation do they need?
- **Governance** — who do they think should own AI decisions?
- **Onboarding** — what would they need to see before trusting AI with a task?

---

## Step 7 — Dashboard and local server

### 7A — HTML dashboard

Generate one self-contained HTML file after Steps 3–6.

**File name:** `[team-name]_persona_ai_readiness_[YYYY-MM-DD].html`

**What to include:**

**Overview tab**
- Team name, product, date
- Table: all personas with coverage scores and agency models
- Heatmap: which attributes are missing across all personas
- Top 3 actions for the team

**One tab per persona**
- Name, role, archetype, coverage score
- Most critical gap with the direct quote that surfaced it
- Agency model per task area
- Automation comfort bars
- Top jobs-to-agents tasks
- Journey map highlights: best stage, riskiest stage, trust cliff
- Full gap table
- 8 research questions

**Cross-persona tab**
- Side-by-side coverage across all personas
- Gaps shared across every persona (these need a batch fix)
- Suggested research order and reason
- Governance risk summary

**Styling:**
- Dark header with team and product name
- Green (#1E8B4E) / Orange (#D46B08) / Red (#C0392B)
- Coverage badge per tab
- No external libraries — all CSS and JS inline
- Tab switching via `switchTab()` function
- Every card includes a traceability footer with source and quote

### 7B — Start the local server

After the file is saved, output these commands:

```bash
cd /path/to/output/folder
python3 -m http.server 8765
# Open: http://localhost:8765/[filename].html
```

If running inside Claude Code (CLI with Bash access):
1. Save the file to a folder the user confirms
2. Launch the server automatically
3. Print the URL

To stop the server: `Ctrl+C`

---

## Step 8 — Signals worth exploring further

Surface 3–5 open questions or tensions worth investigating in future sprints.

**Format:**
**Signal:** [what you observed — cite the source]
→ **Explore:** [what to test or ask]
→ **AI touchpoint:** [which capability this affects]
→ **Risk if skipped:** [what breaks if this isn't validated before launch]

---

## Output rules

1. **No invented statistics.** If no benchmark was provided, write: `[No benchmark provided — validate with your own research]`
2. **No inferring attributes from job titles.** "Manager" doesn't mean HOTL. Only use what's written.
3. **No vague language.** Don't write "users may feel." Write what the persona actually said.
4. **Label everything.** `[From: file.md — "quote"]` for evidence. `[Inferred from archetype]` for framework logic.
5. **Flag incomplete personas up front.** Note which insights are limited as a result.
6. **Coverage scores are conservative.** Vague mentions get ⚠️ Partial, not ✅ Covered.

---

## How to use this with different AI tools

**Claude (Claude Code):** Save to `.claude/commands/persona-universal.md`. Run with `/persona-universal`.

**ChatGPT / GPT-4:** Paste this file as your first message (or as the system prompt). Share your materials in the next message.

**Gemini or other models:** Same as above — paste as system prompt, then share materials.

**Sharing with your team:** Send the `.md` file. Each person runs it independently with their own persona folder. Outputs can be compared side by side.

**Adapting for a new industry:** Replace the 7 archetypes in Step 2 with ones relevant to your domain. Everything else works as-is.

---

## If your persona documents are incomplete

The skill runs on partial information. Missing fields are flagged in the output.

| Field | Required? | If missing |
|-------|-----------|-----------|
| Name / Role | Yes | Pause and ask |
| Goals (at least 2) | Yes | Gap section will be limited |
| Pain points (at least 1) | Yes | Journey map risk section will be limited |
| Tools used | Recommended | Note which tool recommendations can't be made |
| Defining quote | Optional | Trust and failure analysis will be less specific |
| Jobs to be done | Recommended | Jobs-to-Agents section uses archetype defaults only |

---

*persona-universal — version 1.1 — August 2026*
*Works with any LLM. Any industry. Any persona format.*
*Every insight cites its source.*

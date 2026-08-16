# Source Material Library

> The actual reusable content extracted from Osman's three workshops, organized by the module that uses it. This is the raw material the Master Build Plan's "repurpose from" lines point to — captured here so an agent can build a module without fetching live sites.
>
> **How to use it:** each entry has the *original content* (as-is from the workshop) and an *adapt* note. Everything here is professional/Codex-flavored by default. Apply the locked de-vendor decision when building — and on examples, use **both**: teen-relevant examples so learners can actually *do* it, *and* some of the real business examples kept intact as a window into how a real company is trying to get its people to use AI. The professional examples are an asset, not just legacy to strip out — they show teens the real working world they're being prepared for. (Only drop pure workshop-logistics like "bring it to your 1:1 with Osman" — that's not a teaching example.)
>
> Sources: **Work With AI** (WWA), **Advanced Codex** (AC), **Codex Beyond Code** (CBC).

---

## Module 2 · LLM vs Chatbot vs Agent

**[WWA] Chatbot vs. working environment.**
> "A traditional chatbot answers a question. A working AI environment can understand your team's context, reason through complex work, take action across tools, and help build repeatable ways of working."
> "ChatGPT Work and Codex are environments for doing work with AI, not just asking it questions. You set a goal, provide context, review the approach, steer the work, and end with a useful artifact… the conversation is no longer the final product."

*Adapt for teens:* use this for the chatbot→agent rung. Chatbot = you ask, it replies, you do everything with the reply. Agent = you give a goal, it takes actions and hands back the finished thing. Add a teen version ("turn my messy notes into a finished study guide + quiz"), and keep the real "team report" example too — it shows how a workplace actually uses this.

---

## Module 3 · What It's Great At, Where It Breaks

**[CBC] The honest-capabilities frame** — the spine of this module. For each capability the workshop names three things: *where it saves time · typical result · use carefully*. Examples:
- *Image generation* — Saves time: backgrounds, environments, concepts. Use carefully: "accurate product packshots, geometry, finishes, labels, logos, specifications, or embedded copy."
- *Presentations* — Saves time: narrative, content, rough wireframes. Use carefully: "final graphic-design quality… full-slide renders containing unchecked text, claims, and figures."
- *Data* — always pair the chart with the limitation: "the training data is not a substitute for a fresh… check."

**[CBC] The five-minute review checklist** (adapt into the teen "check it when it matters" artifact):
> - The output is clearly treated as a draft, production input, or final deliverable.
> - Real facts, sources, and assets remain accurate.
> - Copy, claims, figures, links, and values match the source and stay editable where required.
> - The result has been checked for quality, consistency, accessibility, and final-format usability.
> - The right owner has approved anything that publishes, shares, or finalizes.

**[CBC] The takeaway framing:**
> "The win is not perfect design on the first try. Codex accelerates research, structure, exploration, and handoff. [Final quality] still needs verified assets, deliberate judgment, and often a human finishing pass."

*Adapt for teens:* keep the three-bucket structure (saves time / rough first draft / must check yourself) and the review checklist. Use both kinds of example — a teen one and a real business one — so they see the pattern in their world and in a real job. The "human finishing pass" idea is the module's core message.

---

## Module 5 · Prompt Engineering

**[AC] The operating brief — six parts** (the "grown-up" prompt; teach as the level-up at the end of the module):
> - **Goal** — What are we trying to accomplish?
> - **Context** — What should it understand about the project, audience, and current state?
> - **Inputs** — What files, tools, apps, APIs, or data should it use?
> - **Constraints** — What must it avoid, preserve, or ask permission before changing?
> - **Deliverables** — What exact artifacts should it produce?
> - **Verification** — What evidence will prove the work is correct?

Copyable structure:
```
Goal:
Context:
Inputs:
Constraints:
Deliverables:
Verification:
```
> "A long prompt is not necessarily a good prompt." · "The goal tells [it] where to go. Verification tells both of you when it has arrived."

**[CBC] The reusable beginner prompt template** (the fill-in scaffold — maps onto Role + Context + Task + Format):
```
Create [output] for [audience].
The purpose is [goal].
Use the attached [source material] as the source of truth.
It should feel [three useful adjectives].
Include [requirements or constraints].
Show me a first version for review before publishing, sending, sharing, or changing access.
```

*Adapt for teens:* lead with the beginner template as the everyday scaffold; introduce the operating brief as the "power version" for bigger tasks. Reuse the operating brief again in Module 10 for agent briefs.

---

## Module 6 · Grounding / Context

**[CBC] Source-of-truth discipline.** Throughout, prompts specify "use the attached [X] as the source of truth" and "use only approved/supplied facts; do not invent." The data example always states the limitation in plain language ("not a substitute for a fresh check").

**[CBC] The handoff/context-carry prompt** (useful for showing how grounding persists across steps):
```
Before starting, summarize:
- what has already been approved
- which source controls the factual content
- which visual or brand choices should stay consistent
- what is still missing or uncertain
- which action requires my approval next
```

*Adapt:* reframe "approved/brand-safe source of truth" as "use *your* real material" (their notes, their doc), and keep a real business example alongside to show why companies care so much about grounding. Pair with the NotebookLM lab (new build). Keep the "always state the limitation" habit.

---

## Module 7 · From Chats to Workflows

**[WWA] Queueing vs. Steering:**
> "When AI is actively working on a task, you do not have to wait for a finished result and start over. You can guide it as it works—interrupting, narrowing the scope, adding constraints, changing the format, or asking it to explain its approach before continuing."

Steering example pattern: start with a first request → while it's running, add a missing metric/constraint "without restarting the task."

**[CBC] Connected workflow (the handoff chain):**
> Source → Signal → Draft → Visual pass → Assembly → Review. "Not every stage needs to produce a final asset. Approved information can move from evidence to draft, visual pass, assembly, and review."

*Adapt:* teach the chain as research → outline → draft → check. Use steering as the live "add what you forgot instead of starting over" move. Pair a teen project with the real campaign example so they see both a relatable use and a real workplace one.

---

## Module 8 · Beyond Text (Multimodal) — strongest existing coverage

**[CBC] The capability tour** (this is nearly the whole module). Seven capabilities, each with *what it's for · useful for · typical result · an example prompt*:
1. **Image generation** — backgrounds, environments, concepts, channel variations.
2. **Presentations** — narrative, headlines, presenter notes, editable charts, wireframes.
3. **Canva** — find/place/adapt approved assets and templates (asset ops, not art direction).
4. **Sites + HTML** — responsive pages, hubs, dashboards, simple tools.
5. **Data + visualize** — inspect data, charts, dashboards, explainers.
6. **Files** — DOCX, PDF, XLSX, CSV; format conversion.
7. **Browser + Computer Use** — inspect/operate a rendered site or app.

**Example prompts to adapt** (originals are Nakamichi campaign — swap the scenario):
- *Image:* "Create a premium 1600×600 banner background. Do not include a product, logo, or text. Leave negative space for editable copy…"
- *Data:* "Use the attached [data] to show which [things] have the strongest signal. Create one clear chart, explain the main observation in plain language, and state the limitation."
- *Site:* "Build a responsive one-page Site from the attached brief. Include the message hierarchy… Show me a reviewable version before publishing."

**[CBC] The consent/limits note:** product imagery, exact claims, and final design "still need verified assets, deliberate judgment, and a human finishing pass." Keep the "is this real?" honesty.

*Adapt:* keep the capability structure and the example-prompt-per-capability format. Add teen outputs (a poster for their event, a chart of their game stats, a one-page site for their club) — and keep a couple of the real campaign examples intact as a window into professional creative work. Fold in real-vs-synthetic/deepfake awareness.

---

## Module 9 · Building Your Own — strongest existing coverage

**[AC] Skills = markdown (the core reveal).** The Agent Skills format:
```
launch-readiness/
├── SKILL.md          # Required: metadata + instructions
├── scripts/          # Optional
├── references/       # Optional
└── assets/           # Optional

---
name: launch-readiness
description: Prepare and verify launch-readiness packages. Use when a product, campaign, or release needs a repeatable pre-launch review.
---
1. Read the operating brief and approved project documents.
2. Run the readiness checks in order.
3. Return findings, evidence, owners, and unresolved risks.
```
> "A skill packages instructions with optional scripts, references, and assets so [it] can repeat a workflow reliably." · "Write the description for discovery: say what the skill does and when [it] should use it."
Reference: agentskills.io (open standard + specification).

**[AC] AGENTS.md — standing project instructions** (a skill's cousin; good for the "config" part). Sections used: Audience/tone · Sources · Working boundaries · Deliverables · Verification. (Full example available — it's the same shape as our own AGENTS.md.)

**[WWA] Plugins & Tools:**
> "Plugins connect the model to information your team already uses: documents, spreadsheets, slides, calendars, messages, files, and APIs."

**[WWA] Publish as Sites:**
> "Sites turn a plan, lesson, dashboard, or prototype into a link people can open and interact with. For many ideas, a small working page is clearer and more engaging than another slide deck."

*Adapt for teens:* lead with "a skill is just a markdown file + a prompt + a little config" using the SKILL.md shape (simplified). Plugins = "giving AI access to your stuff." Publishing a Site = the shareable win. Keep the "write the description so it knows when to use it" tip.

---

## Module 10 · Agents & Automation — strongest existing coverage

**[AC] Plan / Steer / Checkpoint** (three controls for one problem):
- **Plan** (before execution) — "gather context, expose assumptions, compare approaches, agree on verification."
- **Checkpoint** (at review boundaries) — "pause where human judgment can prevent expensive rework or unsafe action." Five checkpoints: plan · first-slice · scope · verification · action.
- **Steer** (during execution) — "correct direction, add context, narrow scope, or change output without restarting." *Note: steering is an in-progress action, not a slash command.*

**[AC] Long-running goals — five things a durable goal needs:**
> Objective · Definition of done · Boundaries · Evidence · Progress cadence.

**[AC] Subagents / delegation (orchestration — top of ladder).**
- *Delegate when:* work is independent · ownership is clear · outputs reviewed separately · parallelism saves real time.
- *Keep it together when:* tightly sequential · agents edit the same files · no clear boundaries · coordination costs more than execution.
- **Subagent return contract:** Scope · Exclusions · Deliverable · Evidence · Handoff.
> "Do not delegate ambiguity. Delegate bounded work."

**[AC] Automate only what you trust — readiness checklist:**
> - The workflow has succeeded manually at least once.
> - Inputs are consistently available.
> - The output contract is stable.
> - Re-running is safe (no duplicate actions).
> - Approval boundaries are defined (read-only prep separated from sending/publishing).
> - Success can be verified (separate signals for generation vs. action).

**[AC] The guiding principle:**
> "The goal is not to remove the human from the workflow. It is to put human judgment at the moments where it matters most."

*Adapt for teens:* teach plan/checkpoint/steer as plain human-in-the-loop control (drop the slash commands). "Bounded agent" = clear goal + clear stopping point + a human check before anything consequential. Frame subagents/parallelism as the "want to run five at once?" top-of-ladder. Keep the automation checklist almost verbatim — it's gold.

---

## Module 11 · Builder Track (optional/advanced)

**[AC] Project briefs — PRD / ADR / TRD:**
- **PRD** (Product Requirements) — Problem · Audience · Requirements · Non-goals · Success criteria.
- **ADR** (Architecture Decision Record) — Context · Decision · Alternatives · Rationale · Consequences.
- **TRD** (Technical Requirements) — Files/interfaces · Implementation stages · Tests · Rollout · QA evidence.

**[AC] VS Code / diff review loop:** Inspect → Plan → Edit (one slice) → Review the diff → Verify (tests/screenshots). Before-editing prompt: "identify files you expect to change, explain why each is involved, identify what should stay untouched." After: "summarize behavioral changes, show verification, identify remaining uncertainty."

**[AC] Integration decision guide — pick the highest-level reliable interface:**
> - **App / connector** — supported service (Drive, Slack, GitHub, Notion, Canva).
> - **Plugin** — a packaged set of skills/apps/tools.
> - **MCP server** — expose custom/internal tools through a standard interface.
> - **Direct API** — deterministic production logic, high-volume.
> - **Computer Use** — operate a visual UI when no programmatic interface exists.
> Before connecting: check "authentication, read/write boundaries, auditability, rate limits, failure behavior, and whether a human must approve consequential actions."

**[WWA] API-key safety** (builder-tier only): individual keys, keep them out of client-side code and repos, rotate exposed credentials; `.env` for local secrets.

*Adapt for teens:* keep as genuinely optional depth. A curious teen can meet PRD/ADR/TRD as "the pro planning docs" and the integration guide as "how AI plugs into other apps," without needing to build them.

---

## Module 12 · Safety & Responsible Use

**[AC] The five checkpoints** (esp. the **action checkpoint** — approve before publishing, sending, deleting, production changes).
**[AC] Automation approval boundaries** — read-only preparation separated from sending/publishing/modifying.
**[AC] Before connecting anything** — auth, read/write boundaries, auditability, rate limits, failure behavior, human approval for consequential actions.
**[CBC] The five-minute review checklist** (see Module 3) and **[CBC] "Permission"** — approve anything that publishes, sends, shares, purchases, deletes, or changes access.
**[WWA] "Do not act" boundaries** — the workshop repeatedly separates preparation from action ("keep this read-only," "keep external actions in draft").

*Adapt for teens:* combine the "human approves consequential actions" theme with the teen-specific privacy/honesty framing (in the Handoff — folding into the Curriculum). The "read-only prep vs. action" split is a clean, teachable safety idea.

---

## Capstone

**[AC] Running capstone — "Product Launch Operating System."** One scenario carried through the whole workshop: Operating brief → Project briefs → Implementation (diff + evidence) → Orchestration (goal + delegation) → Integration decision → Automation (schedule + review gate + success signals).

**[CBC] Running scenario — "Retail Campaign Sprint."** One approved source moved through six capabilities to a reviewable campaign system, with a defined team/audience/source/channels and a "use only supplied facts" boundary.

*Adapt:* keep the *idea* of one scenario carried end-to-end. Offer a teen-relevant capstone (a tool/site/agent for their club, sport, or interest), and show the real business "operating system" scenario as an example of what this looks like at professional scale. Pair with Ayan's demo-day + "leveling not grading" framing (in the Handoff).

---

## Cross-cutting patterns worth reusing anywhere

- **"Show me a version for review before publishing/sending/sharing."** Appears in nearly every prompt — bake this reviewer habit into every build module.
- **"State the limitation in plain language."** The data prompts always append the caveat — reuse for the verify habit.
- **"Use the attached [X] as the source of truth; do not invent."** The grounding reflex.
- **Separate generation from action.** Preparing an output and taking the final action are different steps — verify both.
- **Interactive format ideas** (reusable as blocks): capability cards with an expandable "See an example prompt," the "build one stage, not the whole workflow" try-it, decision guides ("what does the workflow need?"), and downloadable starter packs (brief MD + data CSV + prompt template TXT).

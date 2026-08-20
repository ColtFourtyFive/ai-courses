# AI Fluency Course — Master Build Plan

> The single working document to build from. It consolidates the curriculum (what we teach), the format system (how it's delivered), and the content audit (what we can repurpose vs. build) into a per-module build spec. Open a module, and you have everything needed to start building it.
>
> Companion references: the **Curriculum** doc holds full drafted lesson content for the foundational modules; the **Format & Delivery** doc holds the full product/site spec. This doc is where the actual build work is tracked and specced.

---

## 1. The vision in five lines

- **Who:** teens ages 13–16, framed as early professionals. Parents are the buyers; demo day is the outcome they see. A competitive-edge skill — the proof is a shipped project.
- **The promise:** *"Anything you can imagine, you can build — starting today."*
- **The arc:** modules are ordered by emotional state — **fear → confidence → agency → mastery** — not by difficulty.
- **The wedge:** teach the *mental model* + *prompting as the master key*, so learners can self-teach whatever ships next. Concepts don't expire; tool tricks do.
- **Two layers:** a thin interactive **Core** everyone plays through, and a deep **Codex** (reference) under every module for anyone who wants more.

---

## 2. Decisions to lock before building

1. **How far to de-vendor.** *Recommended:* Core modules teach the concept first and use Claude/ChatGPT/Codex as named examples; the optional Builder tier can stay more Codex-specific. This decides whether existing content is lightly edited or rewritten.
2. **Scenario swap.** Replace every professional scenario in existing content (Nakamichi marketing, Shopify reports, manager 1:1s) with teen-relevant projects (a Discord tool, a study aid, a sports tracker, a small game).
3. **Audience band.** Confirm the exact range (e.g. 13–16 vs. 12–17); it sharpens pacing and examples.
4. **Platform.** Codex is the hands-on starting platform for Modules 0–4. Both Codex and Claude ship as primary tools. Module 4 adds a lens: when to use Codex vs. Claude (harness comparison). This is not a "how to use Codex" course — platform is the delivery vehicle, not the subject.
5. **Format.** Hands-on activities are MP-style: learner gets context + scaffold + step-by-step instructions to complete tasks in their AI platform (Codex or Claude). No in-page sandbox. First deliverable is a simple game — runs alongside/after Module 0 as a self-paced extension of the demystify experience; build in ~a day, add own changes, deploy to shared link for group comparison.
6. **Labs.** Only a FEW required deliverables across the course. Repurpose existing AI upskilling resources rather than build from scratch. Specific lab content TBD after research; pre-course Google Form gathers interest. Timeline set after lab count is fixed.
7. **Capstone timing.** Seed the concept in Module 0 or 1. Learners commit to their specific project at end of Part 1 (after Module 4) — not before, they need to know what's possible first. Build spans Parts 2–4. Demo day is the parent-facing proof.

---

## 3. Existing content — what to repurpose and where

We reviewed the three workshop sites already built and mapped every piece against this plan. This section is the "harvest view" (by source); each module spec below also lists what it pulls.

### What we reviewed

| Site | What it is | Where it lands |
|---|---|---|
| **Work With AI, Not Just Chat With It** | 60-min beginner workshop: ChatGPT Work + Codex as a *working environment* — steering, automations, plugins, publishing Sites. | Mid-course (using AI, workflows, building) |
| **Long-Running Tasks & Systems (Advanced Codex)** | 2.5-hr advanced workshop: operating briefs, plan/steer/checkpoint, goals, multiagent delegation, skills-as-markdown, integrations, automations. | Back of course (agents, orchestration, builder tier) |
| **Codex Beyond Code (Design Studio)** | 90-min demo: Codex for images, slides, Canva, Sites, data viz, docs, browser — plus honest limits and the human finishing pass. | Multimodal + building + capabilities/limits |

**The headline:** all three sit in the **power-user half** of our curriculum (Parts II–III + the advanced tier). None of them build the **foundations** (Part I: demystify, what an LLM is, the core mental models). So we have a strong accelerant for the back half and a from-scratch build for the front half.

**The catch:** all three are **Codex/ChatGPT-specific and written for a professional workplace**. The *ideas and interactive formats* transfer well; the *audience, vendor framing, and examples* need rework for a teen, concept-first course.

### Reuse tiers (legend)

- **[Lift]** — reuse with light edits (de-jargon, swap the example).
- **[Re-level]** — valuable, but needs re-leveling for teens + de-vendoring from Codex-only.
- **[Advanced]** — keep largely as-is, but position as the optional builder/power-user tier for hooked learners.
- **[Park]** — niche or too pro; keep as reference or defer.

### Harvest: *Work With AI* (Osman's)

| Piece | Feeds module | Tier | Rework needed |
|---|---|---|---|
| "Chatbot answers vs. working environment that acts" | 2 (LLM vs Chatbot vs Agent) | [Re-level] | Drop corporate framing; connect to the model→chatbot→agent ladder |
| Queueing vs **Steering** (guide work mid-run) | 7 (Workflows) / 10 (Agents) | [Lift] | Great hands-on concept; swap the report example |
| Scheduled Automations | 7 / 10 | [Re-level] | Teen-relevant automation instead of weekly business brief |
| Plugins & Tools | 9 (Building Your Own) | [Re-level] | Simplify; frame as "giving AI access to your stuff" |
| Publish as **Sites** | 9 | [Lift] | Publishing a shareable thing is perfect for teens as-is |
| Setup checklist (install, connect, permissions, personalization) | Onboarding / 4 | [Re-level] | Consumer accounts, not workspace/admin |
| API key safety, .env | 11 / 12 (Safety) | [Advanced] | Builder-tier only |
| "Prompt then steer it" guided practice | Format: **Guided Lab** block | [Lift] | Reusable lab pattern |

### Harvest: *Advanced Codex* (Osman's)

| Piece | Feeds module | Tier | Rework needed |
|---|---|---|---|
| **Operating brief** (Goal · Context · Inputs · Constraints · Deliverables · Verification) | 5 (Prompting) + 10 (Agents) | [Lift] | Superb spec framework; teach the simple version in 5, full in 10 |
| Plan / Steer / **Checkpoint** pattern | 10 (Agents) | [Re-level] | Strip slash-commands; teach as human-in-the-loop control |
| **Skills = markdown / SKILL.md / Agent Skills format** | 9 (Building Your Own) | [Lift] | Direct match to our "skills are just markdown" reveal |
| Integrations decision guide (API / plugin / MCP / connector / computer use) | 9 / 11 | [Re-level] | Simplify for core; full guide in builder tier |
| Multiagent / subagents / **delegation contracts** | 10 → orchestration | [Advanced] | This *is* our top-of-ladder orchestration content |
| Persistent **goals** (/goal, /status) | 10 | [Re-level] | Concept is great; de-command it |
| Automation readiness checklist | 10 / 12 | [Lift] | "Only automate what you trust" — reusable as-is |
| PRD / ADR / TRD, VS Code diff review, command map | 11 (Builder track) | [Advanced] | Keep for the technical/optional tier |
| Running capstone (Product Launch OS) | Capstone | [Re-level] | Swap for a teen-relevant scenario |

### Harvest: *Codex Beyond Code* (Osman's)

| Piece | Feeds module | Tier | Rework needed |
|---|---|---|---|
| **Capability tour** (image, slides, data, files, sites, browser) | 8 (Beyond Text) + 9 | [Re-level] | This basically *is* Module 8; swap Canva/marketing examples |
| "Where it saves time / where drafts are rough / **human finish**" | 3 (Great at / Breaks) | [Lift] | Excellent capabilities-and-limits material |
| Source-of-truth discipline (approved material only) | 6 (Grounding) + 12 | [Re-level] | Reframe from brand-safety to "use your real material" |
| Reusable prompt template ("Create [output] for [audience]…") | 5 (Prompting) | [Lift] | Clean beginner scaffold |
| Connected workflow / handoffs | 7 (Workflows) | [Lift] | Great chaining example |
| Review / human-finish checklist | 12 (Safety) | [Lift] | Reusable verification habit |
| Capability cards + example prompts + "try one stage" | Format: **Try-It / Mission** blocks | [Lift] | Reusable interactive format |
| Design-inspiration reference shelf | 9 resources | [Lift] | Keep as reference |

---

## 4. How to build a module (shared system)

**Block types** (a module is assembled from these):
Concept (short read/visual) · Demo (worked example) · Try-It (tiny in-page interactive) · Guided Lab (structured exercise) · Mission (open challenge) · Project (bigger self-directed build) · Checkpoint (understanding check) · Share (show-and-tell) · Go Deeper (Codex link).

Interactivity runs on a spectrum: **Try-It → Guided Lab → Mission → Project** (guided → free). Modules move learners rightward as confidence grows. Every module ends in something the learner **keeps or shows**.

**Definition of done for a module** (full — after the joint review):
- [ ] Core content written — short and plain (no textbook walls).
- [ ] At least one interactive block with clear success criteria.
- [ ] One defined artifact the learner keeps.
- [ ] Go Deeper links into the Codex.
- [ ] Safety/verification note where relevant.
- [ ] Piloted with ≥1 real learner; rough timing captured.

**"Ready to review" (what to hit on your own, before the joint session):**
core content drafted + one interactive block sketched + the artifact defined. That's enough to build on together.

---

## 5. How we're splitting the work

See ownership table in §6. Working notes (build order, review cadence, input handoffs) are in `sources/WORKING-NOTES.md`.

---

### Part I — What AI Actually Is

#### Module 0 · Start Here: Demystify
*Owner: Ayan · Status: New · Target: fear → "wait, I made that?"*
- **Covers:** no theory; a first real build in ~15–20 min by describing it in plain English; the reframe that the wall is smaller than it looks; a 20-second map of where the course goes.
- **Repurpose:** the "pick one stage and make a first version" hands-on pattern from *Beyond Code* (format only).
- **Build new:** the exact 5-minute "unlock" build (needs to be jaw-dropping *and* dead-simple); 3–4 teen-relevant build options; the opening framing.
- **Blocks:** Mission (guided) + minimal Concept.
- **Artifact:** a working thing, made day one.

#### Module 1 · What an LLM Actually Is
*Owner: Ayan · Status: New (draft in Curriculum doc) · Target: curiosity, control*
- **Covers:** next-word prediction; trained on a huge amount of text; predicts *patterns, not facts* (→ fluent *and* confidently wrong); tokens; the context window (no memory unless the app adds it); training vs. using it (frozen after training); "large" = billions of parameters; the payoff — not conscious, not magic, just a great predictor.
- **Build new:** the full lesson (drafted); the one-word-change Try-It; a clean prediction diagram.
- **Blocks:** Concept · Demo · Try-It · Checkpoint.
- **Artifact:** experiment log — 3 cases where changing one word flipped the output.

#### Module 2 · LLM vs Chatbot vs Agent
*Owner: Ayan · Input from Osman · Status: Partial · Target: orientation*
- **Covers:** the three-layer ladder — LLM (brain) → chatbot (brain + conversation) → agent (brain + goal + tools + loop); memory/web/tools are features of the *app*, not the model; "ChatGPT" ≠ "GPT"; the **harness** concept (same brain, better body = better results); Claude Code / Codex as agents.
- **Input from Osman:** the "chatbot answers vs. a working environment that acts" section from *Work With AI* (strip corporate framing).
- **Build new:** the LLM/model layer + harness explanation (drafted); the tool-on/off Try-It.
- **Blocks:** Concept · Demo · Try-It · Checkpoint.
- **Artifact:** a labeled diagram of a real assistant — what's model vs. bolted-on.

#### Module 3 · What It's Great At, Where It Breaks
*Owner: Ayan · Input from Osman · Status: Good coverage · Target: healthy skepticism*
- **Covers:** strong at (drafting, summarizing what you give it, explaining, brainstorming, extracting/organizing, code help); weak/risky at (hallucination, confident-wrong, ambiguity, current/private info, multi-step math, bias); the verify habit; the anti-cheating link — you can only lean on what you can catch when it's wrong.
- **Input from Osman:** *Beyond Code*'s "where it saves time / where drafts are rough / human finish" + its review checklist.
- **Build new:** the "break it on purpose" Try-It; teen framing; the verify-checklist template.
- **Blocks:** Concept · Try-It (break it) · Checkpoint.
- **Artifact:** a personal "check it when it matters" checklist.

#### Module 4 · Picking the Right Model
*Owner: Ayan · Status: New · Target: discernment*
- **Covers:** there's no single "best AI"; choose by task/difficulty, speed, cost, privacy, and extras (long context, reasoning); test two options on the *same* few examples instead of trusting one impressive answer.
- **Build new:** a light, current model-landscape overview; the scorecard lab; the head-to-head test. *Note: this content ages fast — keep it principle-based plus a separately maintained cheat sheet.*
- **Blocks:** Concept (brief) · Guided Lab.
- **Artifact:** a reusable model-selection scorecard.

---

### Part II — Using AI Well

#### Module 5 · Prompt Engineering: The Master Skill
*Owner: Ayan · Input from Osman · Status: Good · Target: "the power is in how I ask"*
- **Covers:** prompting = clear thinking + communication (brief a brilliant intern who knows nothing about your situation); the recipe — **Role + Context + Task + Format + Iterate**; a concrete before/after; techniques (give an example, ask it to think step by step, say what *not* to do, break big asks into steps); the **operating brief** as the grown-up version (Goal · Context · Inputs · Constraints · Deliverables · Verification); a good prompt makes output better, not *true*.
- **Input from Osman:** the operating brief (*Advanced Codex*) for the advanced tier; the reusable prompt template (*Beyond Code*) for the beginner scaffold.
- **Build new:** the foundational framing (drafted); the before/after Try-It; the Guided Lab that outputs a reusable prompt.
- **Blocks:** Concept · Try-It · Guided Lab · Share.
- **Artifact:** a reusable prompt they'll use for school this week.

#### Module 6 · Giving It the Right Context (Grounding)
*Owner: Osman · Status: Partial · Target: usefulness, trust-but-verify*
- **Covers:** what it learned in training vs. what you hand it now; how to give it source material; grounded tools (NotebookLM) that answer *only* from your uploads; checking citations; handling conflicting sources.
- **Repurpose:** *Beyond Code*'s source-of-truth discipline → reframe from brand-safety to "use your real material."
- **Build new:** the NotebookLM core lab (upload notes → quiz → study guide); a plain-language RAG preview.
- **Blocks:** Concept (brief) · Guided Lab · Share.
- **Artifact:** a study tool built from their own notes.

#### Module 7 · From Chats to Workflows
*Owner: Osman · Status: Good · Target: thinking in systems*
- **Covers:** one-off chat vs. a repeatable system; breaking a task into steps (research → outline → draft → check); chaining them; where a human should review; making it reusable; the bridge to agents.
- **Repurpose:** **steering** (*Work With AI*) + connected workflow/handoffs (*Beyond Code*) → the core.
- **Build new:** a teen-relevant workflow example; the "run it twice" lab.
- **Blocks:** Concept (brief) · Mission · Share.
- **Artifact:** a repeatable workflow they can re-run.

#### Module 8 · Beyond Text (Multimodal)
*Owner: Osman · Status: Strong (nearly built) · Target: range*
- **Covers:** making and analyzing images, audio, video, data visualizations, documents; the same "predict the next piece" idea applied to pixels and sound; consent, deepfakes, real-vs-synthetic.
- **Repurpose:** *Beyond Code*'s capability tour → basically this whole module (re-level: swap Canva/marketing examples for teen projects; keep the "human finish" honesty).
- **Build new:** teen-relevant capability examples; one shareable multimodal mission.
- **Blocks:** Demo · Mission · Share.
- **Artifact:** something multimodal worth sharing.

---

### Part III — Building

#### Module 9 · Building Your Own
*Owner: Osman · Status: Strong · Target: "building isn't scary — it's this"*
- **Covers:** custom assistants (Projects / Custom GPTs / artifacts); the reveal that **a skill is mostly a markdown file + a good prompt + a little config**; plugins/tools = giving AI access to your stuff; publishing shareable things (Sites); integrations basics (MCP as "USB-C for AI").
- **Repurpose:** skills=markdown / SKILL.md / Agent Skills format (*Advanced Codex*) → the core reveal; plugins + Sites (*Work With AI*); the integrations decision guide (simplified).
- **Build new:** a teen-relevant custom-assistant lab; a small build project.
- **Blocks:** Concept (brief) · Guided Lab · Project · Share.
- **Artifact:** their own working custom assistant.

#### Module 10 · Agents & Automation
*Owner: Osman · Status: Strong · Target: agency*
- **Covers:** an agent = brain + goal + tools + loop; **bounded, human-in-the-loop**; plan / steer / checkpoint control; persistent goals; automate only what you already trust; **orchestration & parallelization + delegation contracts** as the top-of-ladder for hooked learners.
- **Repurpose:** *Advanced Codex* core (plan/steer/checkpoint, goals, subagents/delegation, automation-readiness checklist) → de-command (drop the slash-command drilling) and re-level.
- **Build new:** a simple bounded-agent lab for teens; the orchestration section framed as "want to run five of these at once?"
- **Blocks:** Concept · Mission · Project · Share.
- **Artifact:** a bounded agent that does one real chore, plus a clear sense of its limits.

#### Module 11 · Builder Track (Optional)
*Owner: Osman · Status: Strong (advanced) · Target: depth for the technical*
- **Covers:** talking to models via API; reliable structured output and tool use; embeddings/RAG; evals; PRD/ADR/TRD; VS Code diff review; integration surfaces (API / plugin / MCP / connector / computer use).
- **Repurpose:** the *Advanced Codex* builder pieces → keep largely as-is, positioned as optional depth.
- **Build new:** a gentle on-ramp so a curious non-CS teen can dip a toe in; keep it genuinely optional.
- **Blocks:** Guided Labs · Go Deeper.
- **Artifact:** a small real integration or build.

---

### Part IV — Doing It Right

#### Module 12 · Safety, Privacy & Responsible Use
*Owner: Osman · Input from Ayan · Status: Partial (assemble) · Target: judgment*
- **Covers:** what not to paste (private/sensitive info); hallucination discipline as a habit; prompt-injection basics (hidden instructions); using AI honestly and within the rules that apply to you; the anti-cheating reframe made concrete (direct vs. outsource your thinking); permission/approval boundaries before consequential actions.
- **Repurpose:** checkpoints + permissions + API-key safety (Codex sites) + human-finish/review checklists (all three) → assemble.
- **Input from Ayan:** the teen-specific framing (privacy, school AI policy, honesty) and the anti-cheating reframe.
- **Build new:** the "what could go wrong" lab.
- **Blocks:** Concept · Try-It · Checkpoint.
- **Artifact:** a "what could go wrong" write-up for something they built.

#### Module 13 · Under the Hood (Optional)
*Owner: Ayan · Status: New · Target: depth for the curious*
- **Covers:** how neural networks learn; what a transformer is; how "attention" weighs which words matter — the machinery behind the prediction from Module 1. Framed as *"want to know why the magic works?"* — never a gate.
- **Build new:** the whole thing, visual and accessible; point to 3Blue1Brown and Karpathy as reference.
- **Blocks:** Concept · Go Deeper.
- **Artifact:** optional reflection (enrichment).

---

### Capstone · Build Something Real
*Owner: Osman · Input from Ayan · Status: Partial (re-level) · Target: the "spring," made visible*
- **Covers:** pick an ambitious real thing; define what "good" looks like; build the smallest version that works; test it; note its limits; **demo day**. Concept seeded in Module 0 or 1; learners commit at end of Part 1 (after Module 4); build spans Parts 2–4; demo day is the parent-facing proof.
- **Repurpose:** the running-scenario structure (*Advanced Codex* Product Launch OS; *Beyond Code* campaign sprint) → swap for teen-relevant capstone options.
- **Input from Ayan:** the demo-day format and evaluation-as-portfolio-"leveling" framing.
- **Build new:** teen capstone options.
- **Blocks:** Project · Share.
- **Artifact:** a shipped, demoed project — the portfolio piece.

---

## 6. Ownership at a glance

| # | Module | Owner | Input from | Status | Effort |
|---|---|---|---|---|---|
| 0 | Demystify / Unlock | Ayan | — | New (draft exists) | Medium |
| 1 | What an LLM Actually Is | Ayan | — | New (draft exists) | Medium |
| 2 | LLM vs Chatbot vs Agent | Ayan | Osman | Partial (draft exists) | Medium |
| 3 | Great At / Where It Breaks | Ayan | Osman | Good coverage | Medium |
| 4 | Picking the Right Model | Ayan | — | New | Medium |
| 5 | Prompt Engineering | Ayan | Osman | Good (framing drafted) | Medium |
| 6 | Grounding / Context | Osman | — | Partial | Medium |
| 7 | Chats → Workflows | Osman | — | Good | Medium |
| 8 | Beyond Text (Multimodal) | Osman | — | Strong | Light |
| 9 | Building Your Own | Osman | — | Strong | Medium |
| 10 | Agents & Automation | Osman | — | Strong | Medium |
| 11 | Builder Track (optional) | Osman | — | Strong | Light |
| 12 | Safety & Responsible Use | Osman | Ayan | Partial | Medium |
| 13 | Under the Hood (optional) | Ayan | — | New | Medium |
| — | Capstone | Osman | Ayan | Partial | Light |

**The balance:** Ayan owns 7 modules (0–5, 13) — the concept/foundation spine and the demystify voice. Osman owns 8 (6–12, capstone) — the applied, building, and safety half. By effort it's even: Ayan's front-half modules already have drafts in the Curriculum doc, and Osman's extra module is offset by three of his being light adaptations (8, 11, capstone) of workshops he already built. Total ≈ 14 effort-units each.

---


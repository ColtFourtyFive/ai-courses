# Module 04 · Picking the Right Model
**Owner:** Ayan  ·  **Status:** New  ·  **Emotional target:** discernment
**Research brief:** `research-briefs/module-04-research-brief.md`  ·  **Research notes:** `research-notes/module-04.md`

## Spec (from sources/Master-Build-Plan.md)
- **Covers:** no single "best AI"; choose by task/difficulty, speed, cost, privacy, extras (long context, reasoning); test two options on the *same* few examples.
- **Build new:** a light, current model-landscape overview; the scorecard lab; the head-to-head test. *Content ages fast — keep it principle-based + a separately maintained cheat sheet.*
- **Blocks:** Concept (brief) · Guided Lab.
- **Artifact:** a reusable model-selection scorecard.

---

# Module 4 · Picking the Right Model
Emotional target: discernment   ·   Est. time: ~20 min

## Why this matters
There's no single "best AI." There's the right tool for the task. Picking by hype — or by habit — means you'll regularly get worse results than you could have, from the exact same options you already have access to. This module gives you a framework for choosing instead of guessing.

## What you'll walk away able to do
- Explain why different AI models exist and when each tier is the right call
- Compare two models on the same task and articulate what the better one did differently
- Have a reusable scorecard for picking the right tool for any task

---

## Concept

### There's no single best AI

Every major AI provider — Anthropic (Claude), OpenAI (ChatGPT), Google (Gemini) — offers roughly three tiers of model. Different names, same shape:

| Tier | What it's for | What you trade |
|---|---|---|
| **Fast / light** (Haiku, Flash, mini variants) | Quick tasks: lookups, reformatting, simple Q&A | Lower quality on complex tasks |
| **Standard** (Sonnet, standard GPT, Gemini standard) | Most things: drafts, explanations, brainstorming | The daily driver |
| **Heavy** (Opus, GPT top-tier, Gemini Pro) | Complex reasoning, careful arguments, high-stakes output | Slower, more likely paywalled |

Plus a special mode most providers now offer: **reasoning mode** (Claude's extended thinking, OpenAI's o-series descendants, Gemini's thinking mode). Visible "thinking" before it answers. Better at math and multi-step logic. Not always better for quick questions or creative writing — the overhead isn't worth it there.

**The principle that doesn't expire:** use the lightest model that gets the job done. Using a heavy model for everything is like driving a pickup truck to buy a sandwich — you can, but you're wasting something. And using a fast model for something that needs careful reasoning is how you get arguments that sound good but fall apart under scrutiny.

---

### How to choose: four questions

**1. How hard is this task, really?**
Quick and simple (look something up, reformat text, answer a clear factual question) → fast model is fine.
Medium (draft an essay, summarize a document, serious brainstorming) → standard model.
Complex or high-stakes (multi-step math, careful argument, something where being wrong really matters) → heavy model or reasoning mode.

**2. Do I need it right now?**
Waiting at my keyboard → skip reasoning mode; use the fastest model that works.
Walking away and coming back → use whatever tier the task actually warrants.

**3. Is anything sensitive in what I'm pasting?**
Real full name + personal details, another person's private info, school credentials, medical or financial information → stop. Remove the sensitive part or don't use AI for this task. This applies regardless of which model you pick.
Nothing sensitive → proceed.

**4. Does this task need a special capability?**
Images, audio, or video → confirm the model is multimodal before pasting.
Current / live information → confirm web search is on.
Code to run → confirm a code interpreter is available.
None of the above → standard text model is fine.

---

### One real-world example

Early AI teams at companies discovered the same thing you're learning now: routing every task to the most powerful (and slowest, and most expensive) model produced mediocre results at high cost. The teams that did best learned to tier it — fast model for simple queries, heavy model for the tasks that actually needed it. They got better results on the complex tasks and stopped burning time and budget on the easy ones. The principle scales from a company's entire workflow down to a single homework session: match the model to the task.

---

## Guided Lab: Head-to-Head Test

You're going to run the same prompt in two different tools (or two tiers of the same tool) and see the difference. Not feel — *see*, with specific criteria.

**Step 1 — Pick your task (2 min)**

Choose something real you have coming up: a test, a project, an essay. Write one sentence describing it:
> *"I have a [history essay / AP Bio quiz / math unit test] in [X days] and I want to [do well / not fall behind / finish it without cramming]."*

**Step 2 — The test prompt**

Use this exact prompt in both tools. Do not change it between rounds:

> *"I have a [paste your sentence here]. Give me a concrete, day-by-day study plan that's actually doable. Be specific — not generic advice."*

**Round 1 (5 min):** Run it in Tool A. Read the full output. Fill in the scorecard below.

**Round 2 (5 min):** Run the exact same prompt in Tool B — a different app, a different tier, or the same tool with reasoning mode on. Read the full output. Fill in the scorecard.

> **If you only have one tool:** run it with reasoning mode on vs. off. Or try "You are an expert tutor" added at the start vs. no setup. It's not a perfect two-model test, but it still builds the habit of testing before trusting.

**Step 3 — Score both outputs (3 min)**

For each output, score 1–3 on each dimension:

| | Tool A | Tool B |
|---|---|---|
| **Specificity** — concrete steps, not vague advice? | __ / 3 | __ / 3 |
| **Fit to your timeline** — works in the time you actually have? | __ / 3 | __ / 3 |
| **Confidence calibration** — does it hedge what it can't know, or claim certainty about your exam? | __ / 3 | __ / 3 |
| **Would I actually use it?** — could I start right now? | __ / 3 | __ / 3 |
| **Total** | __ / 12 | __ / 12 |

**Step 4 — Write two sentences**

1. *"[Tool / tier that scored higher] did better because it ___."* (name one specific thing, not just "it was better")
2. *"Neither did well at ___."* (there's usually something)

**Success looks like:** you can point to one concrete thing the better output did differently — not "it felt more helpful" but "it broke the plan into specific days instead of giving me a topic list."

---

## The one thing to remember
*There's no best AI — there's the right one for the task. Test, don't guess.*

---

## Artifact

**Your model-selection scorecard.** Save this somewhere you'll actually use it — pinned in your notes app, at the top of a recurring doc, on your phone.

---

```
MODEL SELECTION SCORECARD
Task: _________________________________

Q1 — How hard is this task?
 [ ] Quick / simple    → fast model OK
 [ ] Medium            → standard model
 [ ] Complex / stakes  → heavy model or reasoning mode

Q2 — Do I need it right now?
 [ ] Yes, waiting at keyboard   → skip reasoning mode
 [ ] No, walking away           → reasoning mode OK if task warrants

Q3 — Anything sensitive I'm pasting?
 [ ] Yes   → STOP. Remove the sensitive part first.
 [ ] No    → proceed

Q4 — Special capability needed?
 [ ] Images / audio / video?   need multimodal
 [ ] Current / live info?      need web search ON
 [ ] Code to run?              need code interpreter
 [ ] None of the above         standard text is fine

MY PICK: ________________________________
(e.g., "Standard model, web search on, no reasoning mode needed")
```

---

> **The model landscape changes fast.** Specific model names, which tier costs what, and what's available on free plans shift constantly. For a current snapshot — which tools are in which tier right now — see the **Model Landscape cheat sheet in the Codex** (updated quarterly). This scorecard stays valid regardless of what ships next; the cheat sheet keeps the tool names current.

---

## Go Deeper →
*(Verify links before publishing — URL check needed.)*
- **Anthropic — "Models overview"** Anthropic's own description of what each Claude tier is for and when to use it. → https://docs.anthropic.com/en/docs/models-overview
- **OpenAI — "Models"** Same from OpenAI's side — pair with the Anthropic link to show the tier principle isn't brand-specific. → https://platform.openai.com/docs/models
- **Simon Willison's blog** An independent (no vendor affiliation) AI commentator who writes accessibly about practical model differences. Search for "model selection" or "when to use a smaller model." → https://simonwillison.net


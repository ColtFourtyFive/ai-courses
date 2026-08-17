# Module 04 · Picking the Right Model
**Owner:** Ayan  ·  **Status:** Ready to review  ·  **Emotional target:** discernment
**Research brief:** `research-briefs/module-04-research-brief.md`  ·  **Research notes:** `research-notes/module-04.md`

## Spec (from sources/Master-Build-Plan.md)
- **Covers:** no single "best AI"; choose by task/difficulty, speed, cost, privacy, extras (long context, reasoning); test two options on the *same* few examples.
- **Build new:** a light, current model-landscape overview; the scorecard lab; the head-to-head test. *Content ages fast — keep it principle-based + a separately maintained cheat sheet.*
- **Blocks:** Concept (brief) · Guided Lab.
- **Artifact:** a reusable model-selection scorecard.

---

# Module 4 · Picking the Right Model
Emotional target: discernment   ·   Est. time: ~25 min

## Why this matters
There's no single "best AI." There's the right tool for the task you're actually doing. Picking by hype — or by habit — means you'll regularly get worse results than you could have, from the exact same options you already have access to. This module gives you a framework for choosing instead of guessing.

## What you'll walk away able to do
- Explain why different AI models exist and when each tier is the right call
- Run a proper 3-prompt test battery and describe what the difference actually was
- Use a reusable scorecard for picking the right tool for any task

---

## Concept

### There's no single best AI

Every major AI provider — Anthropic (Claude), OpenAI (ChatGPT), Google (Gemini) — offers roughly three tiers of model. Different names, same shape:

| Tier | What it's for | What you trade |
|---|---|---|
| **Fast / light** (Haiku, Flash, mini variants) | Quick tasks: lookups, reformatting, simple Q&A | Lower quality on complex tasks |
| **Standard** (Sonnet, standard GPT, Gemini standard) | Most things: drafts, explanations, brainstorming | The daily driver |
| **Heavy** (Opus, GPT top-tier, Gemini Pro) | Complex reasoning, careful arguments, high-stakes output | Slower, more likely paywalled |

Plus a special mode most providers now offer: **reasoning mode** (Claude's extended thinking, OpenAI's o-series, Gemini's thinking mode). The model thinks out loud before it answers. Better at multi-step math and logic. Not always worth it for quick questions or creative writing — the overhead isn't justified there.

**The principle that doesn't expire:** use the lightest model that gets the job done. Using a heavy model for everything is like driving a pickup truck to get a sandwich — technically fine, but wasteful. And using a fast model for something that needs careful reasoning is how you get arguments that sound confident but fall apart when you look closely.

---

### How to choose: six questions

**1. How hard is this task, really?**
Quick and simple (look something up, reformat text, answer a clear factual question) → fast model is fine.
Medium (draft an essay, explain a concept, serious brainstorming) → standard model.
Complex or high-stakes (multi-step math, careful argument, something where being wrong really matters) → heavy model or reasoning mode.

**2. Do I need it right now?**
Waiting at my keyboard → skip reasoning mode; use the fastest model that works.
Walking away and coming back → use whatever tier the task actually warrants.

**3. Does cost matter for this task?**
Free tier, unlimited tasks → any model that gets the job done.
High volume (running the same thing many times) → lean toward faster, cheaper tiers.
One important, low-frequency task → cost is irrelevant; use whatever tier fits.

> **Context on cost:** between the cheapest and most expensive tiers, the price difference can be 18x to 66x per token processed. For a company sending millions of queries, this is enormous. For a student, it mostly means knowing which models are paywalled on free plans. *Flag for live verification before publishing — model pricing changes frequently.*

**4. Is anything sensitive in what I'm pasting?**
Real full name + personal details, another person's private info, medical or financial information, school credentials → stop. Remove the sensitive part or don't use AI for this. This applies regardless of which model you pick — the tier doesn't change the privacy question.
Nothing sensitive → proceed.

**5. Does this task need a special capability?**
Images, audio, or video → confirm the model is multimodal before pasting.
Current / live information → confirm web search is on.
Code to run → confirm a code interpreter is available.
None of the above → standard text model is fine.

**6. Is this a long-document task?**
Some models can hold a full novel's worth of text in a single conversation. Others cut off much sooner. If you're working with a long document — a whole textbook chapter, a lengthy report, 50,000 words of research — check whether the model supports long context before pasting. Using a model with a short context window for a long document means it quietly ignores the parts that didn't fit.

---

### One real-world example

The open-source project RouteLLM (github.com/lm-sys/RouteLLM — available to verify) benchmarked exactly this approach: automatically routing easy queries to smaller models and hard queries to larger ones. Their published benchmarks show 40–80% cost reduction with little or no quality loss on the easy queries. The insight scales from a company's entire API budget down to a single homework session: match the model to the task.

And this is the part worth holding onto: the easy queries didn't suffer. A fast model handles simple questions just as well as a heavy model. The heavy model earns its place on the hard questions — and *only* there.

---

## Guided Lab: 3-Prompt Head-to-Head Test

One impressive answer doesn't tell you much. One bad model can nail an easy question; one great model can stumble on a poorly framed one. The only way to actually compare two tools is to run the *same set of prompts* through both and score what you see.

You're going to run three prompts in two different tools (or two tiers of the same tool) and score each one. Not feel — *see*, with specific criteria.

**Before you start — pick your two tools (2 min)**

Tool A and Tool B: two different apps, two different tiers of the same app, or the same tool with reasoning mode on vs. off.

> **If you only have one tool:** run it with reasoning mode on vs. off. Or try adding "You are an expert tutor" at the start vs. no setup. It's not a perfect two-model test, but it still builds the habit.

---

**The three prompts**

Run each one in *both* tools. Copy and paste the exact wording — no changes between rounds.

**Prompt 1 — Simple task**
> *"What is the capital of Australia?"*

**Prompt 2 — Medium task**
> *"Explain how compound interest works, in plain language, with one example using real numbers."*

**Prompt 3 — Complex / personal task**
> *"Help me think through whether I should take AP Chemistry next year. I'm currently getting a B in regular chemistry, I'm interested in medicine as a future career, and I already have 3 other AP classes. What should I consider?"*

**Why these three?** A fast model handles Prompt 1 just as well as a heavy model — the answer is the same either way. Prompt 2 is where you start to see quality differences in explanation and structure. Prompt 3 is where reasoning depth matters: the model has to hold several factors in tension, weigh trade-offs, and not just list talking points. Don't judge a model by one easy question.

---

**Score each prompt in each tool (1–3 per dimension)**

#### Prompt 1 — Simple task

| | Tool A | Tool B |
|---|---|---|
| **Accuracy** — correct answer? | __ / 3 | __ / 3 |
| **Clarity** — stated it cleanly, no fluff? | __ / 3 | __ / 3 |
| **Total** | __ / 6 | __ / 6 |

#### Prompt 2 — Medium task

| | Tool A | Tool B |
|---|---|---|
| **Accuracy** — compound interest explained correctly? | __ / 3 | __ / 3 |
| **Plain language** — could someone with no finance background follow it? | __ / 3 | __ / 3 |
| **Concrete example** — used real numbers, not vague generalities? | __ / 3 | __ / 3 |
| **Total** | __ / 9 | __ / 9 |

#### Prompt 3 — Complex / personal task

| | Tool A | Tool B |
|---|---|---|
| **Depth of reasoning** — did it actually hold multiple factors in tension, or just list them? | __ / 3 | __ / 3 |
| **Personalisation** — did it address the specific details given (B in chemistry, medicine interest, 3 other APs)? | __ / 3 | __ / 3 |
| **Honest uncertainty** — did it hedge what it can't know (your energy levels, your school's support), or claim certainty? | __ / 3 | __ / 3 |
| **Actionable** — would you actually know what to do or ask next after reading it? | __ / 3 | __ / 3 |
| **Total** | __ / 12 | __ / 12 |

---

**Write three sentences when you're done**

1. *"On Prompt 1, both tools were [roughly equal / noticeably different] because ___."*
2. *"The biggest quality gap I saw was on Prompt [2 / 3], where [Tool A / Tool B] did better because it ___."* (Name the specific thing — not "it was better" but "it broke down the trade-offs instead of just listing them.")
3. *"One dimension I now check that I didn't before is ___."* (cost, context length, reasoning mode, accuracy on personal-context questions — pick one that actually came up.)

---

**Success looks like:** you ran all 3 prompts in both tools and can point to:
- One prompt where both tools were roughly equal (usually Prompt 1)
- One prompt where you noticed a specific quality difference — something in the wording, structure, or accuracy — and you can name it specifically
- One dimension you now check that you didn't before (cost, context length, reasoning mode, etc.)

**If all 3 prompts got identical scores in both tools:** run Prompt 3 again but add more complexity: *"I also have a chronic health condition that might affect my energy levels for a heavy course load."* That almost always produces a visible quality gap — because now the model has to weigh something it can't just look up.

---

## The one thing to remember
*There's no best AI — there's the right one for the task. Test on a few examples, don't guess from one.*

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

Q3 — Does cost matter for this task?
 [ ] Free tier, unlimited use           → any model that works
 [ ] Running it many times (high vol)   → lean toward faster/cheaper tier
 [ ] One-off, important task            → cost irrelevant; use best fit

Q4 — Anything sensitive I'm pasting?
 [ ] Yes   → STOP. Remove the sensitive part first.
            (This applies regardless of which model you pick.)
 [ ] No    → proceed

Q5 — Special capability needed?
 [ ] Images / audio / video?    need multimodal
 [ ] Current / live info?       need web search ON
 [ ] Code to run?               need code interpreter
 [ ] None of the above          standard text is fine

Q6 — Long document involved?
 [ ] Yes (long chapter, big report, 10,000+ words)
         → check model supports long context before pasting
 [ ] No  → proceed

MY PICK: ________________________________
(e.g., "Standard model, web search on, no reasoning mode needed")
```

---

> **The model landscape changes fast.** Specific model names, which tier costs what, and what's available on free plans shift constantly. For a current snapshot, see the **Model Landscape cheat sheet in the Codex** (updated quarterly). This scorecard stays valid regardless of what ships next.

---

## Go Deeper →
*(Verify links before publishing — URL check needed.)*
- **Anthropic — "Models overview"** Anthropic's own description of what each Claude tier is for and when to use it. → https://docs.anthropic.com/en/docs/models-overview
- **OpenAI — "Models"** Same from OpenAI's side — pair with the Anthropic link to show the tier principle isn't brand-specific. → https://platform.openai.com/docs/models
- **RouteLLM** The open-source project that benchmarked cost-aware model routing — 40–80% cost reduction with negligible quality loss on easy queries. Good reading for the technically curious. → https://github.com/lm-sys/RouteLLM
- **Simon Willison's blog** An independent (no vendor affiliation) AI commentator who writes accessibly about practical model differences. Search for "model selection" or "when to use a smaller model." → https://simonwillison.net

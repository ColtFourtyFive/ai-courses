# AGENTS.md — Building Course Module Content

> Drop-in operating brief for any agent (or person) building one module of the AI Fluency course. Read this, then your module's spec, then build.

## Your job
Produce the actual learner-facing content for **one module** — the explanations, activities, and artifact — to *ready-to-review* quality. You're writing the module, not planning it.

**The course end-state:** an emotional promise ("anything you can imagine, you can build") and an intellectual one — mental models that don't expire when the tools do. Write toward both.

## Read first — and what to take from each
1. **AI Fluency Master Build Plan** → your module's spec: what it covers, its blocks, its artifact, what to repurpose, its owner. *This is your assignment — start here.*
2. **AI Fluency Course Curriculum** → the teaching substance; for the foundational modules it has full drafted content to build from. Also your reference for voice and for how each concept is explained.
3. **AI Fluency Format & Delivery** → what each block type is (Concept, Demo, Try-It, Guided Lab, Mission, Project, Checkpoint, Share, Go Deeper) and how a module is shaped.
4. **Source Material Library** → the actual workshop content to repurpose, *if* your spec lists a "repurpose from." Pull the exact framework, prompt, or checklist named — don't paraphrase it from memory.

## What you produce — module output shape
Write the module as markdown in this shape. Fill only the blocks your spec calls for — not every module uses every block.

```
# Module N · [Title]
Emotional target: [...]   ·   Est. time: [~X min]

## Why this matters
[1–2 real sentences — why the learner should care. Not cutesy.]

## What you'll walk away able to do
- [plain objective]
- [plain objective]

## [Each block the spec lists — Concept / Demo / Try-It / Lab / Mission / Project / Checkpoint / Share]
[The actual content.
 - Concept: short, plain, analogy-first.
 - Demo: what the learner watches happen.
 - Try-It / Lab / Mission / Project: exact instructions + what success looks like.
 - Checkpoint: a quick understanding check.]

## The one thing to remember
[Single-sentence takeaway.]

## Artifact
[What the learner keeps or shows.]

## Safety / verify note  (if relevant)

## Go Deeper →
[Link(s) into the reference layer / Codex.]
```

## Voice (non-negotiable)
Audience: teens ~13–16, no CS background, some nervous about AI. Frame them as early professionals — these skills transfer directly to real work. Plain, warm, direct, a little dry humor. Talk *to* them, never down to them, never corporate or academic.
- **Demystify first:** a plain-English "here's what's really going on" before any jargon. **Analogy before definition.** Short sentences.
- **No textbook walls** — break concept with a demo or try-it. Honest about limits (it can be confidently wrong). No hype, no fear-mongering, no condescension.
- Every module ends in something the learner **keeps or shows**.

Good: *"An LLM is a next-word guessing machine that got scary good by reading a huge chunk of the internet."*
Not this: *"Large Language Models leverage transformer-based architectures to model token probability distributions."*

## Writing Standard (enforce on every sentence, before you call anything done)

Every draft defaults to AI-slop unless you actively cut it. This isn't a style preference — it's a hard rule, checked sentence by sentence.

**Ban outright:**

- **Throat-clearing openers.** Never open a section, paragraph, or module with a sentence that delays the content. Banned: "In today's world," "Let's dive in," "Imagine a world where," "We live in an age of…" Start with the actual point.
  - Not this: *"In today's world, AI is transforming how we learn."*
  - This: *"An LLM predicts the next word. That's it."*

- **Previewing and recapping.** Don't tell the reader what you're about to say or what you just said. Banned: "In this section we'll cover…", "As we discussed…", "Now that we understand X, let's…", "By the end of this you'll be able to…" Just say the thing — the reader doesn't need a table of contents restated in prose.

- **Hedging and filler.** Cut on sight: "it's important to note," "it's worth mentioning," "essentially," "basically," "in order to" (→ "to"), "the fact that" (→ delete or restate directly), "when it comes to." These add length, not meaning.

- **Fancy words when a plain word works.** If a simpler word means the same thing, the fancy one is wrong. "Utilize" → "use." "Leverage" as a verb → "use." "Facilitate" → "help." No exceptions for sounding smart.

- **Vague abstraction and scaffolding-about-substance.** Don't describe that a concept is important, interesting, or surprising — show the concept and let it be those things. If a sentence describes the shape of an idea instead of stating the idea, delete it.
  - Not this: *"Here's the part that surprises most people: how prediction produces intelligence."*
  - This: *"Guessing the next word in a chemistry textbook well means absorbing how chemistry works."*

- **Writerly flourishes.** A plain sentence trying to sound clever is still slop — just quieter. Watch for reaching-for-effect phrasing and stacked em-dashes used for dramatic pause. Plain doesn't mean occasionally-poetic.
  - Not this: *"The intelligence isn't separate from the prediction — it's the prediction, scaled up to a size that's genuinely hard to picture."*
  - This: *"The intelligence isn't separate from the prediction. It is the prediction, just at a huge scale."*

- **Empty engagement bait.** No fake enthusiasm, no exclamation-point energy, no "the cool part is…", no "here's the fun bit." If it's genuinely interesting, the content shows that — you don't need to announce it.

**Require:**

- **Plain English.** Write like a sharp person explaining something to a smart friend — not a textbook, not a corporate deck, not a TED talk.
- **Every sentence earns its place — this is not a length target.** If a sentence can be deleted without losing meaning, delete it. But "earns its place" is not the same as "fewer sentences": if cutting slop reveals a section no longer fully teaches the concept, that's a sign the section needs more real substance, not a sign the cut worked. A shorter draft that quietly drops teaching content is a worse failure than a longer one that's slightly loose. Judge every draft on voice AND depth, together — never trade one for the other.
- **Respect the reader.** These are intelligent 13–16-year-olds with baseline common sense. Don't over-explain the obvious, don't hand-hold, don't talk down.
- **Lead with the point, support it after.** State the claim, then back it up — don't build up to it.
- **Concrete over abstract.** Show the real example, the real number, the real sentence — don't describe that an example exists.

**Self-check — run this before marking any draft ready to review:**
1. Re-read every sentence. If it opens with a banned throat-clearing or preview phrase, cut the phrase and start with the content underneath it.
2. Find every hedge word above. Delete it or rewrite the sentence without it.
3. Find every sentence that describes an idea ("here's the surprising thing," "notice that…") instead of stating it. Rewrite to state it directly.
4. Read it out loud. If a sentence sounds like it could appear in a thousand other AI-written documents, rewrite or delete it. Watch for quiet flourishes too — a sentence can be slop-free and still be reaching for effect instead of just saying the thing.
5. Check depth, separately from voice. After cutting slop, does every concept the spec requires still get fully taught? If a section reads clean but thin, add real substance back — don't mistake shortness for success.

## Explain recurring concepts exactly as the Curriculum does
Don't invent new analogies for these — reuse the canonical framings:
- **LLM** = a next-word prediction engine trained on huge text. (Analogy: a brilliant intern who's read everything but knows nothing about your situation yet.)
- **Model vs. app/harness** = brain vs. body (memory, web, tools, the loop). "ChatGPT" ≠ "GPT."
- **Chatbot** = brain + conversation. **Agent** = brain + goal + tools + a loop ("a chatbot answers; an agent does").
- **Prompting** = clear thinking made explicit (Role + Context + Task + Format + Iterate).
- **Hallucination** = predicts *plausible*, not *true* → fluent and sometimes confidently wrong; verify what matters.
- **Skill** = mostly a markdown file + a good prompt + a little config.

## Examples — use BOTH real and teen-relevant
Two kinds of example, both valuable — don't strip one out:
- **Teen-relevant** (a Discord tool, a study guide, game-stat charts, a one-page site for their club) — so they can actually *do* it and see themselves in it.
- **Real business** (kept from the workshops — a company getting its team to use AI, a real reporting or campaign workflow) — a window into how AI is actually used in a real job and what a workplace expects. These are motivating and give real-world insight.

Rule of thumb: give a teen example they can act on, **and** keep or introduce a real one so they see the professional version. Frame the real ones as *"here's how an actual company does this."* (Only drop pure workshop-logistics like "bring it to your 1:1" — that's not a teaching example.)

## Build workflow
1. Read your module's spec in the Master Build Plan.
2. Pull any "repurpose from" material from the Source Material Library.
3. Draft the **Core** content — short — for each block the spec lists.
4. Build **one interactive block** with clear success criteria.
5. Define the **artifact** the learner keeps.
6. Add **Go Deeper** links and a **safety/verify** note if relevant. Estimate rough timing.

## Guardrails (the locked decisions)
- **De-vendor:** concept-first, name tools as examples. Codex is the hands-on starting platform for Modules 0–4; both Codex and Claude ship as primary tools. Module 4 includes a lesson on when to use each (harness comparison). Do not strip Codex references from early modules — they belong there.
- **Examples:** use both teen-relevant and real business ones (see above).
- **Audience:** use the confirmed age band for pacing and examples.
- **Don't pad.** If it reads like a textbook, it's wrong.

## Done means
- **Ready to review:** core content drafted + one interactive block sketched + artifact defined.
- **Fully done (after human review):** short core content · one interactive block with success criteria · defined artifact · Go Deeper links · safety/verify note where relevant · piloted with ≥1 real learner and timing captured.

# AI Fluency — Course Curriculum

> One course that takes someone from "AI scares/confuses me" to "I understand how it works, I use it well, and I can build with it." Rigorous on the concepts, plain in the language, hands-on wherever it helps — and never dry for the sake of it.

This document combines two drafts into one: the rigorous concept-and-skills curriculum, and the demystify-first, fear-killing framing. It keeps the substance of the first and the accessibility of the second.

**Who this is for.** Teens 13–16, no CS background. Frame them as early professionals — these skills transfer directly to real work, and that's the value prop. Parents are the buyers; demo day is the outcome they see.

---

## How the course works

**Two layers.**
- **The Core** — what every learner goes through. Tight, clear, and built around *understanding by doing* wherever the topic allows.
- **Go Deeper** — an optional reference layer under each module for anyone who wants the full technical detail. You never need it to move forward; it's there when curiosity hits.

**Three honest rules about format.**
1. Some modules are concept modules — you read, watch a demo, and learn. That's fine and necessary; you can't skip understanding how the thing works. We keep those *short and clear*, not textbook-dry.
2. Most modules pair a concept with something you actually do or build, because AI is learned by using it.
3. Every module ends with one thing you can *keep or use* — a prompt, a tool, a small build. Progress is always visible.

**The through-line.** Early modules exist to kill the fear and demystify. Middle modules build real skill. Later modules hand over real power. By the end, "anything you can imagine, you can build" is meant literally. And more durably: learners understand the stack well enough to evaluate and use whatever comes next. Tool tricks expire; the mental model doesn't.

---

## Curriculum map

| Part | # | Module | You walk away able to… | Format |
|---|---|---|---|---|
| **Start** | 0 | Start Here: Demystify | Use AI without fear; build one small real thing | Do |
| **I. What AI Actually Is** | 1 | What an LLM Actually Is | Explain what an LLM is and isn't, in plain words | Read + do |
| | 2 | LLM vs Chatbot vs Agent | Tell the three apart and know which you're using | Read + do |
| | 3 | What It's Great At, Where It Breaks | Predict when to trust, check, or reject output | Read + do |
| | 4 | Picking the Right Model | Choose a model by task, not hype | Do |
| **II. Using AI Well** | 5 | Prompt Engineering: The Master Skill | Reliably get great output on the first or second try | Read + do |
| | 6 | Giving It the Right Context | Make AI useful on *your* material, not generic | Do |
| | 7 | From Chats to Workflows | Turn a one-off chat into a repeatable system | Do |
| | 8 | Beyond Text (Multimodal) | Work with images, audio, and video | Do |
| **III. Building** | 9 | Building Your Own | Build a custom assistant (skills = markdown + prompt) | Build |
| | 10 | Agents & Automation | Build a bounded agent that does a real task | Build |
| | 11 | Builder Track (optional) | Use APIs, structured output, RAG, and evals | Build |
| **IV. Doing It Right** | 12 | Safety, Privacy & Responsible Use | Spot risks and use AI accountably | Read + do |
| | 13 | Under the Hood (optional) | Understand *why* it works (neural nets, transformers) | Read |
| **Capstone** | — | Build Something Real | Ship and demo a real project | Build |

---

# Part I — What AI Actually Is

## Module 0 — Start Here: Demystify

**Why this matters.** Most people freeze because AI feels like magic or a threat. It's neither. Before any theory, you'll build one small, real thing — so the wall is gone before we explain anything.

**Do it.** Pick something you actually want and describe it in plain English to an AI assistant: a quiz on your favorite game, a tool that rewrites your texts in different tones, a tiny web page. Watch it get made. That's the whole point — you just made something by describing it.

**Walk away with.** A working thing, and the realization that the barrier was smaller than it looked.

---

## Module 1 — What an LLM Actually Is

**Why this matters.** Everything else in the course makes sense once you understand this one thing. Get it, and AI stops being magic and starts being a tool you can control.

**What you'll understand.**
- What an LLM is in one sentence
- Why it's so fluent — and why it can be confidently wrong
- What "tokens," "context," and "training" actually mean
- Why it doesn't remember you or look things up (unless an app adds that)

**The core idea.**

An **LLM (Large Language Model)** is, at its heart, a **next-word predictor**. You give it some text; it predicts what word most plausibly comes next, adds it, and repeats. That's it. Everything impressive it does is a consequence of doing that *extremely* well.

How did it get good? It read an enormous amount of text — a huge chunk of the internet, books, code — and played one game billions of times: *guess the next word*. Get good enough at that game and you can write essays, answer questions, and produce working code, because all of those are just "what word comes next" over and over.

The single most important consequence: **it predicts patterns, it does not look up facts.** There's no dictionary or database inside it. This is why it writes so smoothly — and *also* why it can invent a fake quote or a wrong date with total confidence. A smooth, wrong answer is still a good next-word guess. Fluency is not truth. (We'll build a habit around this in Module 3.)

A few terms, demystified:
- **Tokens.** It doesn't read letters or whole words exactly like you; it breaks text into chunks called tokens (roughly word-pieces). Not important day to day — just know that's the unit it works in.
- **Context.** It only "knows" two things: what it absorbed during training, and what's in front of it right now — the current conversation, called the **context window**. It does **not** remember you between chats unless the app bolts on a memory feature.
- **Training vs. using it.** *Training* is the expensive, one-time process where it learned. *Using it* (called inference) is every time you type something. It's frozen after training — it does not learn from your chats.
- **Why "large."** It has billions of internal dials (**parameters**) it tuned while learning. Bigger often means more capable, but not always — and bigger also means slower and pricier.

**The demystify payoff:** it's not conscious, it's not thinking like you, and it's not magic. It's a very, very good pattern-predictor. Once that clicks, the fear drains out and the control comes in — because now you know what you're actually working with.

**Try it.** Run one prompt three times, changing a single word of the setup each time (a character's mood, the setting, the audience). Watch how much the output shifts. You're seeing prediction respond to context in real time.

**The one thing to remember.** *An LLM predicts plausible text from patterns — that's why it's fluent, and why it can be confidently wrong.*

**Go deeper →** pretraining vs. post-training vs. inference; how tokenization works; context windows and why long context degrades.

---

## Module 2 — LLM vs Chatbot vs Agent

**Why this matters.** People say "ChatGPT," "the model," "AI," and "an agent" as if they're the same thing. They're not — they're three different things stacked on top of each other. Knowing which one you're dealing with tells you what to expect and how to use it. This is the distinction that makes you sound like you actually understand AI.

**What you'll understand.**
- The three layers: model, chatbot, agent
- Why features like memory and web search belong to the *app*, not the model
- What "harness" means and why the same model can feel very different in different tools

**The core idea.**

Think of it as three levels, each wrapping the one before it.

**1. The LLM — the brain.** This is the raw next-word predictor from Module 1. On its own it takes text in and puts text out. That's *all* it can do. It can't click a link, can't remember past the current message, can't use a tool. Examples of models: GPT-5, Claude Opus, Gemini. When people name a "model," this is the layer they mean.

**2. The chatbot — the brain in a conversation.** Wrap that brain in an app that keeps a conversation going, and maybe adds memory, web search, and file uploads, and you get a chatbot: **ChatGPT, Claude.ai, Gemini** (the apps). Here's the reveal most people miss: **browsing, memory, and tools are features of the app, not the brain.** The exact same model, used raw through a developer connection, has none of those unless someone adds them. So "ChatGPT" is not the same thing as "GPT" — one is the product, one is the brain inside it.

**3. The agent — the brain with hands and a to-do list.** Give the brain a set of tools *and* a loop — where it can make a plan, take an action, look at the result, and decide the next step, working toward a goal with much less hand-holding — and you have an agent. The difference in one line: **a chatbot answers you; an agent goes and does something.** Examples: Claude Code and Codex (agents built for programming), and computer-use agents that click around a screen.

The whole ladder:
> **LLM** = brain. **Chatbot** = brain + conversation. **Agent** = brain + goal + tools + a loop.

**One more term that makes you sound sharp: the harness.** The "body" wrapped around the brain — the app, the tools, the loop, the instructions — is called the **harness** (or scaffold). The brain provides the raw intelligence; the harness decides how much of it you actually get to use. This is why the *same* model can feel dramatically better in one tool than another: a great harness gets more out of the same brain. It's also why "which model" matters less than people think, and "how it's wired up" matters more.

**Try it.** In one assistant, ask it something only today's internet would know (a score, a price) with web access off, then on. Same brain, different powers — you just watched the *app* layer, not the model, change what's possible.

**The one thing to remember.** *The model is the brain; the app and its tools are the body. Most of how "smart" an AI feels is the body, not the brain.*

**Go deeper →** the application/harness layer in detail; how tools and memory are actually attached; why Claude Code and Codex differ even on similar models.

---

## Module 3 — What It's Great At, Where It Breaks

**Why this matters.** Using AI well is mostly knowing when to trust it, when to check it, and when to walk away. This is also the real anti-cheating skill: you can't lean on something you can't catch when it's wrong.

**What's covered.**
- **Strong at:** rewriting and drafting, summarizing material you give it, explaining concepts, brainstorming, extracting and organizing info, coding help.
- **Weak at / risky:** making up facts and citations (hallucination), sounding certain while being wrong, ambiguous or underspecified tasks, current or private info it never saw, multi-step math and logic, inherited bias.
- **The core habit:** confidence is *generated*, not earned. When the answer matters, verify it — check a source, redo the math, ask for its reasoning.

**Try it.** Deliberately get it to fail: bait a fake citation, a wrong calculation, a confident answer to a trick question. Then write your own short "check it" list for when accuracy actually matters.

**The one thing to remember.** *Fluent and confident is not the same as correct. Verify what matters.*

**Go deeper →** hallucination causes, risk tiers, red-teaming, bias, data freshness.

---

## Module 4 — Picking the Right Model

**Why this matters.** There isn't one "best AI." There's the right tool for the task. Knowing how to choose stops you from overpaying, waiting too long, or trusting the wrong one.

**What's covered.** Choosing by task type and difficulty, speed, cost, privacy, and whether you need extras like long context or reasoning. The idea of testing two options on the *same* few examples instead of trusting one impressive answer. **And a concrete harness comparison:** when to reach for Codex vs. Claude — the two primary tools learners are already using — and why the answer depends on the task, not on which is "better."

**Try it.** Run the same real task in both Codex and Claude; score each on the same criteria; articulate why you'd pick one over the other for this type of task.

**Walk away with.** A simple scorecard you can reuse to pick a model for any task, plus a personal framework for when Codex vs. Claude fits your work.

**Go deeper →** the model landscape (general, reasoning, small, embedding, open-weight), hosted vs. local.

---

# Part II — Using AI Well

## Module 5 — Prompt Engineering: The Master Skill

**Why this matters.** This is the highest-leverage skill in the whole course. The model's ceiling is high; your prompt decides how much of it you actually reach. Same model, vague prompt → mediocre. Same model, sharp prompt → excellent. And once you truly get this, almost everything else — custom assistants, agents — is mostly *this* skill applied.

**What you'll understand.**
- Why prompting is communication, not magic words
- The reliable recipe for a strong prompt
- A few techniques that noticeably improve results
- Why a good prompt still doesn't make it truthful

**The core idea.**

Forget "secret prompts" and cheat sheets. **Prompting is clear thinking, made explicit.** The best mental model: you're briefing a brilliant intern who has read almost everything but knows *nothing* about your specific situation. Your job is to brief them well.

The reliable recipe — most good prompts have these five pieces:

1. **Role** — who it should act as. *"You are a patient chemistry tutor."*
2. **Context** — the situation and the goal. *"I'm a 10th grader who missed the lesson on moles and has a quiz Friday."*
3. **Task** — exactly what you want. *"Explain moles with one everyday example, then give me 3 practice questions."*
4. **Format** — how you want it back. *"Keep it under 150 words. No jargon."*
5. **Iterate** — refine based on what you get. *"Good, but make the example about cooking and add one harder question."*

See the difference:
- *Weak:* "explain climate change."
- *Strong:* "You're a science teacher explaining to a curious 9th grader. Explain why climate change happens using one everyday analogy, in under 120 words, then check my understanding with two questions."

Same model. Completely different result.

A few techniques worth knowing (kept short):
- **Show, don't just tell.** Give an example of what you want. Even one example transforms output.
- **Ask it to think step by step** for anything involving logic or math — it genuinely improves accuracy.
- **Say what you *don't* want.** "Don't use bullet points. Don't add a conclusion."
- **Break big asks into steps** instead of one giant request.

**The unlock:** once you internalize that the quality is in *how you ask* — and that you fully control that — you stop being at the mercy of the AI. This is the barrier that, once broken, opens everything after it.

**One caution.** A great prompt makes output *better*, not *true*. Module 3's verify habit still applies.

**Try it.** Take one weak prompt you'd normally type, rewrite it with the five-piece recipe, and run both. Save the improved one — you'll reuse it.

**The one thing to remember.** *Prompting is clear communication. Role + context + task + format + iterate beats a vague ask every time.*

**Go deeper →** prompting as specification, testing prompts against fixed examples, building reusable prompt templates with known failure cases.

---

## Module 6 — Giving It the Right Context (Grounding)

**Why this matters.** Out of the box, AI answers from generic patterns. Feed it *your* material and it answers about *your* stuff — your notes, your document, your data. This is where it goes from party trick to genuinely useful.

**What's covered.** The difference between what a model learned in training and what you hand it right now; how to give it source material; using a tool like NotebookLM that answers *only* from what you upload (so it can't wander off your material); checking citations and handling conflicting sources.

**Try it.** Load your real class notes into a grounded tool, then have it quiz you and build a study guide that stays true to your material.

**Walk away with.** A working study tool built from your own notes.

**Go deeper →** retrieval, provenance, and a preview of how search-over-your-documents (RAG) works under the hood.

---

## Module 7 — From Chats to Workflows

**Why this matters.** Most people use AI one message at a time. The leap in power is turning a task into a repeatable *system* you can run again and again.

**What's covered.** Breaking a task into steps (e.g., research → outline → draft → check) and running them as a chain instead of one messy prompt; identifying where a human should review; making the workflow reusable. This is also the conceptual bridge to agents.

**Try it.** Build a repeatable workflow for something real in your life — a study routine, a content process, a research method — and run it twice.

**Go deeper →** workflow design: inputs, decisions, handoffs, review points, ownership.

---

## Module 8 — Beyond Text (Multimodal)

**Why this matters.** Modern AI isn't just text — it sees, hears, and generates images, audio, and video. Same core idea, wider canvas.

**What's covered.** Working with images (make and analyze), audio, and video; the same "predict the next piece" idea applied to pixels and sound; a straight talk on consent, deepfakes, and telling real from synthetic.

**Try it.** Make something multimodal you'd actually want to share.

**Go deeper →** modality-specific quality, provenance, synthetic-media risk.

---

# Part III — Building

## Module 9 — Building Your Own

**Why this matters.** This is where "using AI" becomes "building with AI" — and where the biggest myth dies. Building a custom assistant isn't a separate, scary, code-heavy thing.

**What's covered.** Building a custom assistant (Claude Projects / Custom GPTs / artifacts) and the key reveal: **a custom "skill" is mostly a markdown file — plain text instructions — plus a good prompt and a little configuration.** Which means building comes right back to Module 5: it's mostly clear instructions. Guided along the way.

**Try it.** Build a custom assistant that does one specific thing your way, every time.

**Walk away with.** Your own working custom assistant.

**Go deeper →** structured output, tool use, connecting external apps (MCP).

---

## Module 10 — Agents & Automation

**Why this matters.** Agents are the frontier — AI that plans and *acts*. By now you have the foundation to build one instead of just hearing the buzzword.

**What's covered.** What an agent really is (brain + goal + tools + loop, from Module 2), building a **bounded** agent with a clear stopping point and a human check before anything consequential, and why simpler workflows are often enough. For the hooked learner, this is where **orchestration and running agents in parallel** live — the top of the ladder, reached only once you're ready for it.

**Try it.** Build a small, bounded agent that does one real chore end-to-end.

**Walk away with.** A working agent, plus a clear sense of its limits and safety boundaries.

**Go deeper →** planning, tools, permissions, stopping conditions, multi-agent orchestration.

---

## Module 11 — Builder Track (Optional)

**Why this matters.** For the technically curious who want to build real software with AI, not just use it. Fully optional; the course is complete without it.

**What's covered (as depth, not required):** talking to models through an API, getting reliable structured output and tool use, searching over private documents (embeddings + RAG), and measuring quality with evaluations.

**Go deeper →** the full builder chapters: APIs and structured output, embeddings/search/RAG, evals and observability.

---

# Part IV — Doing It Right

## Module 12 — Safety, Privacy & Responsible Use

**Why this matters.** Real fluency includes judgment. This is threaded lightly from Module 1, then handled directly here.

**What's covered.** What not to paste into AI (private/sensitive info); hallucination discipline as a habit; the basics of prompt injection (how someone can trick an AI through hidden instructions); using AI honestly and within the rules that apply to you; and the anti-cheating reframe made concrete — directing AI vs. outsourcing your thinking.

**Try it.** Take one thing you built earlier and write a short "what could go wrong here" for it — privacy, accuracy, misuse.

**The one thing to remember.** *Safety isn't a separate topic — it's part of doing good work.*

**Go deeper →** access control, data handling, IP, auditability, governance.

---

## Module 13 — Under the Hood (Optional)

**Why this matters.** For the learner who's now hooked and wants to know *why* the magic works.

**What's covered.** How neural networks learn, what a transformer is, and how "attention" lets a model weigh which words matter — the machinery behind the next-word prediction you met in Module 1. Framed as satisfying curiosity, never as a requirement.

**Go deeper →** neural networks, transformers, attention, and the research lineage.

---

## Capstone — Build Something Real

The concept is introduced in Module 0 or 1; learners commit to their specific project at the end of Part 1 (after Module 4), once they understand what's possible. Building spans Parts 2–4.

Pick something ambitious you actually care about and build it using everything: a real tool, agent, or workflow that solves a real problem for you or someone you know. Define what "good" looks like, build the smallest version that works, test it, and note its limits.

Then **demo it** — to the group, and to the people who care (parents/sponsors). This is the proof and the portfolio piece: the moment the whole arc becomes visible, to you and to them.

---


# Module 02 · LLM vs Chatbot vs Agent
**Owner:** Ayan  ·  **Status:** Partial (draft in Curriculum.md)  ·  **Emotional target:** orientation
**Input from:** Osman  ·  **Research brief:** `research-briefs/module-02-research-brief.md`  ·  **Research notes:** `research-notes/module-02.md`

## Spec (from sources/Master-Build-Plan.md)
- **Covers:** the three-layer ladder — LLM (brain) → chatbot (brain + conversation) → agent (brain + goal + tools + loop); memory/web/tools are features of the *app*, not the model; "ChatGPT" ≠ "GPT"; the **harness** concept; Claude Code / Codex as agents.
- **Input from Osman:** the "chatbot answers vs. working environment that acts" material (Source-Material-Library.md → Module 2).
- **Build new:** the LLM/model layer + harness explanation (draft exists); the tool-on/off Try-It.
- **Blocks:** Concept · Demo · Try-It · Checkpoint.
- **Artifact:** a labeled diagram of a real assistant — model vs. bolted-on.

---

# Module 2 · LLM vs. Chatbot vs. Agent
Emotional target: orientation   ·   Est. time: ~20 min

## Why this matters
People say "ChatGPT," "the model," "AI," and "an agent" as if they mean the same thing. They don't — they're three different things stacked on top of each other. Knowing which layer you're dealing with tells you what to expect, why it's behaving the way it is, and how to get more out of it. This is the distinction that makes you sound like you actually understand AI.

## What you'll walk away able to do
- Tell the three layers apart and name which one you're using at any moment
- Explain why memory and web search belong to the *app*, not the model
- Know what the harness is and why it matters more than most people think

---

## Concept

### The ladder: three levels, each wrapping the one before

**Level 1 — The LLM: the brain.**

This is the raw next-word predictor from Module 1. On its own, it takes text in and puts text out. That's *all* it can do. It can't click a link, can't remember your name from last week, can't search the web, can't open a file. Powerful — but with no connection to the outside world on its own.

Examples of models at this layer: **GPT** (OpenAI's family), **Claude** — which comes in tiers like Opus, Sonnet, Haiku, and Fable — and **Gemini** (Google's family). Version names and numbers change often; what matters is recognizing *these* as the brain layer.

**Level 2 — The chatbot: the brain in a conversation.**

Wrap that brain in an app that keeps a conversation going, and you get a chatbot. The apps you've probably used: **ChatGPT, Claude.ai, Gemini.** They feel more capable because the app is layering things on top of the raw model — memory of past chats, web search, file uploads, image generation.

Here's the reveal most people miss: **browsing, memory, and tools are features of the *app*, not the brain.** The exact same model, accessed without those layers, has none of them. Turn web search off in your assistant of choice, and the brain is still there — but the capability disappears, because it was the app providing it, not the model.

So "ChatGPT" ≠ "GPT." One is the product. One is the brain inside the product. They're different things.

**Level 3 — The agent: the brain with hands and a to-do list.**

Give the brain a set of tools *and* a loop — where it can plan, take an action, check the result, and decide the next step, working toward a goal without you manually advancing every move — and you have an agent.

The difference in one line: **a chatbot answers you; an agent goes and does something.**

Here's what that looks like in practice: ask a chatbot to turn your messy notes into a study guide. It gives you a draft in the chat — you copy it out, format it, save it, add the quiz yourself. Now imagine handing an agent the same goal — "turn these notes into a finished study guide with a quiz at the end, saved as one file." An agent doesn't answer you; it reads, drafts, combines, and saves the finished thing, then hands it back. The goal is the input; the done artifact is the output.

A real team works the same way. A traditional chatbot answers "summarize this report." An agent-style workflow goes and pulls the data, drafts the report, and hands back a finished document to review — the conversation is no longer the product.

Real examples of agents you can actually try: **Claude Code** and **Codex** (both built for programming tasks). There are also computer-use agents that operate a screen directly, clicking around like a person would.

The ladder in one line:
> **LLM** = brain. **Chatbot** = brain + conversation. **Agent** = brain + goal + tools + a loop.

### The harness: why the same brain can feel very different

The "body" wrapped around the brain — the app, its tools, the loop, all the wiring — has a name: the **harness**. It's the layer that decides how much of the brain's intelligence you actually get to use.

This is why the *same* underlying model can feel dramatically more capable in one tool than another. A well-built harness gets more out of the same brain. It's also why "which model?" matters less than most people think, and "how it's wired up" matters more.

Think of it like a musician. You wouldn't judge their talent purely in isolation — you'd also care about what instrument they have, whether the sound system is good, what the venue is like. The harness is all of that.

---

## Demo

Here's the same brain, two different harness settings.

Open any AI assistant that has a **web search toggle** (Claude.ai, ChatGPT, and Gemini all have this — look for a web or search icon in the interface).

Ask it something only today's internet would know: a live sports score, a current stock price, something that happened in the news this week.

1. **Search off.** Ask the question. Watch it either decline ("I don't have real-time data"), hedge with a caveat, or guess from its training — possibly wrong or outdated.
2. **Search on.** Ask the exact same question. Watch it search and come back with a current, cited answer.

Same brain both times. What changed was the harness — specifically, one tool the app chose to give the brain access to.

---

## Try-It

Do the demo yourself.

1. Pick a question only today's internet would know: a live score, a current price, something from this week's news.
2. Turn web search **off**. Ask it. Note what it says.
3. Turn web search **on**. Ask the exact same question. Note what it says now.
4. Fill in this sentence: *"When I turned search off, it [___]. When I turned it on, it [___]. What changed wasn't the brain — it was ___."*

Keep that filled-in sentence — it's the checkpoint for this module.

**What success looks like:** you can name which layer changed (hint: not the model) and you can say what that layer is called.

---

## Checkpoint

1. Someone says "ChatGPT just got smarter — it can browse the web now." What's the more accurate way to describe what actually happened?
2. What's the difference between a chatbot and an agent, in one sentence each?
3. What is the harness, and why does it matter?

---

## The one thing to remember
*The model is the brain; the app and its tools are the body. Most of how "smart" an AI feels is the body, not the brain.*

---

## Artifact

**A labeled diagram of a real assistant.** Pick one AI tool you actually use. Sketch or write out its two layers:

- **The brain (model layer):** what the raw model does on its own — text in, text out, no memory, no tools.
- **The body (harness layer):** everything the app bolts on. For each feature you name (memory, web search, file access, integrations), add the label: *"added by the app, not the model."*

If you want to go further: add a third ring for the agent layer — mark it *"added by the loop."*

The test: can you point at any feature and say clearly whether it lives in the brain or the body?

---

## Go Deeper →
- **Anthropic — "Building Effective Agents"** What distinguishes a true agent from a workflow. → https://www.anthropic.com/research/building-effective-agents
- **Simon Willison — "I think 'agent' may finally have a widely agreed-upon definition"** The best short definition of agents, crowdsourced from 200+ competing definitions. Near-identical to the one in this module. → https://simonwillison.net/2025/Sep/18/agents/
- **Anthropic — "Effective harnesses for long-running agents"** Anthropic's own engineers writing about harnesses — where the term comes from and what a good one looks like. → https://www.anthropic.com/engineering/effective-harnesses-for-long-running-agents
- **Hugging Face — "Harness, Scaffold, and the AI Agent Terms Worth Getting Right"** If you want the precise 2026 field distinctions between model, scaffold, harness, and agent — this is where to go. → https://huggingface.co/blog/agent-glossary
- **Claude Help Center — Memory and search in Claude.ai** See how a real product describes its memory and search as app features, not model features — exactly the point of this module. → https://support.claude.com/en/articles/11817273-use-claude-s-chat-search-and-memory-to-build-on-previous-context

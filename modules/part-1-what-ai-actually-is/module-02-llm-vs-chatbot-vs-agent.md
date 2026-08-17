# Module 02 · LLM vs Chatbot vs Agent
**Owner:** Ayan  ·  **Status:** Ready to review  ·  **Emotional target:** orientation
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
- Recognize when something is acting like a chatbot versus acting like an agent

---

## Concept

### The ladder: three levels, each wrapping the one before

**Level 1 — The LLM: the brain.**

This is the raw next-word predictor from Module 1. On its own, it takes text in and puts text out. That's *all* it can do. It can't click a link, can't remember your name from last week, can't search the web, can't open a file. Powerful — but with no connection to the outside world on its own.

Examples of models at this layer: **GPT** (OpenAI's family), **Claude** — which comes in tiers like Opus, Sonnet, Haiku — and **Gemini** (Google's family). Version names and numbers change often; what matters is recognizing *these* as the brain layer.

**Level 2 — The chatbot: the brain in a conversation.**

Wrap that brain in an app that keeps a conversation going, and you get a chatbot. The apps you've probably used: **ChatGPT, Claude.ai, Gemini.** They feel more capable because the app is layering things on top of the raw model — memory of past chats, web search, file uploads, image generation.

Here's the reveal most people miss: **browsing, memory, and tools are features of the *app*, not the brain.** The exact same model, accessed without those layers, has none of them. Turn web search off in your assistant of choice, and the brain is still there — but the capability disappears, because it was the app providing it, not the model.

So "ChatGPT" ≠ "GPT." One is the product. One is the brain inside the product. They're different things.

**Level 3 — The agent: the brain with hands and a to-do list.**

This is where something changes fundamentally. Listen to how Osman's workshop team described the difference, because they nailed it:

> "A traditional chatbot answers a question. A working AI environment can understand your team's context, reason through complex work, take action across tools, and help build repeatable ways of working."

That's not just a better chatbot. It's a different thing entirely. Here's the full picture from the same workshop:

> "You set a goal, provide context, review the approach, steer the work, and end with a useful artifact… the conversation is no longer the final product."

In plain teen terms: **a chatbot gives you the answer. An agent goes and does the thing.**

Here's what that looks like in a real workplace. A team using a traditional chatbot might ask it to "summarize this report." It spits out a summary in the chat. They then copy it, format it, email it, build the follow-up actions themselves. An agent-style setup is different: you give it the goal, it pulls the data, drafts the document, formats it, and hands back something you can actually use — the conversation wasn't the product, the finished document was.

And here's what it looks like for you. Imagine you want to turn a mess of class notes into a study guide. With a chatbot, you get a draft in the chat — you copy it out, format it, save it, write your own quiz. With an agent, you hand over the notes and the goal, and it reads, drafts, formats, builds the quiz, and delivers the finished file. Same notes. Same goal. Different layer.

Give the brain a set of tools *and* a loop — where it can plan, take an action, check the result, and decide the next step, working toward a goal without you manually advancing every move — and you have an agent.

The ladder in one line:
> **LLM** = brain. **Chatbot** = brain + conversation. **Agent** = brain + goal + tools + a loop.

Real examples of agents you can actually try: **Claude Code** and **Codex** (both built for programming tasks, where the agent reads your code, plans a fix, makes changes, and checks if they worked — all in a loop). There are also computer-use agents that operate a screen directly, clicking around like a person would.

### The harness: why the same brain can feel very different

The "body" wrapped around the brain — the app, its tools, the loop, all the wiring — has a name: the **harness**. It's the layer that decides how much of the brain's intelligence you actually get to use.

This is why the *same* underlying model can feel dramatically more capable in one tool than another. A well-built harness gets more out of the same brain. It's also why "which model?" matters less than most people think, and "how it's wired up" matters more.

Think of it like a musician. You wouldn't judge their talent purely in isolation — you'd also care about what instrument they have, whether the sound system is good, what the venue is like. The harness is all of that.

---

## Demo

**The same goal, two layers.**

Watch what happens when the same request hits a chatbot versus an agent. You're not doing anything here yet — just read this and notice what's different.

**Goal:** "Turn my messy notes into a finished study guide with a quiz at the end."

---

**Chatbot response** (brain + conversation):

The chatbot reads your notes and produces a study guide as text in the chat. It hands you a document. You copy it out, format it, save it, create the quiz yourself based on what it wrote.

The conversation is the product. Everything after it is your job.

---

**Agent response** (brain + goal + tools + loop):

The agent reads your notes, creates a structured outline, drafts each section, formats it as a document, builds a 10-question quiz at the end, saves the finished file, and hands you the complete artifact. You review it.

The conversation isn't the product — the finished thing is.

---

Same notes. Same goal. The chatbot answered you. The agent did the thing.

This is the agent loop made visible: plan → act → check → decide next step → repeat. You set the goal. It runs the loop. You review the result.

---

## Try-It

Now you do something. This one shows you the harness layer directly — specifically, what changes when the app turns a tool on or off.

**Step 1.** Open any AI assistant that has a **web search toggle** (Claude.ai, ChatGPT, and Gemini all have this — look for a web, search, or globe icon in the interface).

**Step 2.** Pick a question only today's internet would know: a live sports score, a current stock price, something that happened in the news this week.

**Step 3.** Turn web search **off**. Ask your question. Write down what it says. (It'll probably decline, hedge, or guess from old training data.)

**Step 4.** Turn web search **on**. Ask the exact same question. Write down what it says now.

**Step 5.** Fill in this sentence:

> *"When I turned search off, it [___]. When I turned it on, it [___]. What changed wasn't the brain — it was ___."*

Keep that sentence — it's your checkpoint for this module.

**What success looks like:** you can name which layer changed (the harness — the app layer, not the model) and you can explain why the brain itself didn't change at all.

**Want to see the agent loop in action?** Open Claude.ai and give it a multi-step problem: plan a project, work through a complex set of decisions, or debug something step by step. Watch it plan before it acts. Notice when it checks its own work before continuing. That plan → act → check sequence is the agent loop made visible — you're watching Level 3 in real time.

---

## Checkpoint

1. Someone says "ChatGPT just got smarter — it can browse the web now." What's the more accurate way to describe what actually happened?
2. What's the difference between a chatbot and an agent, in one sentence each?
3. What is the harness, and why does it matter?
4. A friend gives the same goal to a chatbot and an agent. The chatbot hands back a draft in the chat. The agent hands back a finished file. Which layer is responsible for that difference, and what is that layer called?

---

## The one thing to remember
*The model is the brain; the app and its tools are the body. Most of how "smart" an AI feels is the body, not the brain.*

---

## Artifact

**A labeled diagram of a real assistant.** Pick one AI tool you actually use. Fill in the template below.

```
MY AI TOOL: ___________________________

BRAIN LAYER (the model — text in, text out, no memory, no tools)
Raw capability: ____________________________
What it CAN'T do on its own: ______________

BODY LAYER (the harness — what the app adds)
□ Memory of past conversations    → added by the app
□ Web search / live information   → added by the app
□ File uploads / document reading → added by the app
□ Image generation                → added by the app
□ Other: _____________________    → added by the app

IS THIS AN AGENT? (Does it have a goal + tools + a loop?)
□ Yes — it can plan and take actions toward a goal on its own
□ No — it answers messages but doesn't act independently
□ Somewhere in between — explain: ________________
```

The test: can you point at any feature and say clearly whether it lives in the brain or the body? If you can, you've got the module.

---

## Go Deeper →
- **Anthropic — "Building Effective Agents"** What distinguishes a true agent from a workflow. → https://www.anthropic.com/research/building-effective-agents
- **Simon Willison — simonwillison.net** Search for "agents" — Willison writes the clearest short takes on what the term actually means and how practitioners use it. (No specific post linked here — his blog is frequently updated and the search is the reliable entry point.) *(Verify before publishing.)*
- **Anthropic — "Effective harnesses for long-running agents"** Anthropic's own engineers writing about harnesses — where the term comes from and what a good one looks like. → https://www.anthropic.com/engineering/effective-harnesses-for-long-running-agents *(Verify before publishing.)*
- **Claude Help Center — Memory and search in Claude.ai** See how a real product describes its memory and search as app features, not model features — exactly the point of this module. → https://support.claude.com/en/articles/11817273-use-claude-s-chat-search-and-memory-to-build-on-previous-context *(Verify before publishing.)*
- **Hugging Face blog** — Search "agent glossary" for precise distinctions between model, scaffold, harness, and agent as the field uses them in practice. *(Verify before publishing.)*

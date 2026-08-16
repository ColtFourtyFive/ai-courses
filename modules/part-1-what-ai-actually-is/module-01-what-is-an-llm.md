# Module 01 · What an LLM Actually Is
**Owner:** Ayan  ·  **Status:** New (full draft in Curriculum.md)  ·  **Emotional target:** curiosity, control
**Research brief:** `research-briefs/module-01-research-brief.md`  ·  **Research notes:** `research-notes/module-01.md`

## Spec (from sources/Master-Build-Plan.md)
- **Covers:** next-word prediction; trained on huge text; predicts *patterns, not facts* (→ fluent AND confidently wrong); tokens; context window (no memory unless the app adds it); training vs. using it (frozen after training); "large" = billions of parameters; the payoff (not conscious, not magic, just a great predictor).
- **Repurpose from:** none — foundations absent from existing content.
- **Build new:** full lesson (draft in Curriculum.md); the one-word-change Try-It; a clean prediction diagram.
- **Blocks:** Concept · Demo · Try-It · Checkpoint.
- **Artifact:** experiment log — 3 cases where changing one word flipped the output.

---

# Module 1 · What an LLM Actually Is
Emotional target: curiosity, control   ·   Est. time: ~20 min

## Why this matters
Everything else in this course makes sense once you understand this one thing. Get it, and AI stops being magic — it becomes a tool you can actually control.

## What you'll walk away able to do
- Explain what an LLM is and isn't, in plain English
- Explain why it's so fluent — and why it can be confidently wrong
- Know what tokens, the context window, and training actually mean

---

## Concept

### The core idea: a next-word predictor

Fill in the blank: *Peanut butter and ___.*

You just did what a Large Language Model does — you predicted what word most plausibly comes next.

An **LLM (Large Language Model)** is, at its heart, a **next-word predictor**. You give it some text; it predicts what word most plausibly comes next, adds it, and repeats. That's it. Everything impressive it does is a consequence of doing that *very, very well*.

Think of it as autocomplete on your phone — the thing that suggests your next word as you type — except it read a huge chunk of the internet, billions of books, and a mountain of code before you ever typed a single character. Same idea, wildly different scale.

The best mental model: **a brilliant intern who's read almost everything but knows nothing about your specific situation.** It can draft your essay, explain quantum physics, write code in a dozen languages — because it's seen all of it. But it doesn't know who you are, what grade you're in, what your class did last Tuesday, or whether the quote it just wrote actually exists. It predicts *plausible*, not *true*.

### Why it's fluent — and why it can be confidently wrong

Here's the thing that trips people up. The model predicts patterns, not facts. There's no dictionary, no database, no internal fact-checker. It's asking: *given everything I've read, what word most plausibly comes next?*

A smooth, wrong answer is still a good next-word guess.

This is why it writes so well — and why it can invent a fake quote, a wrong date, or a non-existent book citation with total confidence.

Imagine asking an AI to help with a history essay. It produces a perfect-looking quote from a historical figure: specific name, specific date, specific source. Completely legit-looking. The quote doesn't exist anywhere. If you pasted it in without checking, you'd have submitted fabricated evidence stated with total authority — because the AI stated it with total confidence.

A real company learned this the hard way. Air Canada's website chatbot told a customer he could buy a full-price ticket after a family death and claim a bereavement discount retroactively. That was false — the real policy required requesting the discount *before* travel. He relied on the chatbot's confident, fluent answer, got denied the discount, and took Air Canada to court. A Canadian tribunal ruled Air Canada responsible for what its chatbot said, and they had to pay. The chatbot wasn't lying. It was predicting. But the smooth, confident answer wasn't true.

**Fluency is not truth.** We'll build a habit around this in Module 3.

> **A quick note on "thinking" models.** Some AI today shows a "thinking" or "reasoning" process before it gives you a final answer. That's still next-word prediction — it's just doing more of it, step by step, before committing. Same game, longer scratchpad. Module 13 goes deeper if you're curious why.

### A few terms, demystified

**Tokens.** The model doesn't read letters or whole words the way you do. It breaks text into chunks called tokens — roughly word-pieces. "Unbelievable" might become two tokens; a short word might be one. Not important day to day — just know that's the unit it works in.

**The context window.** It only "knows" two things: what it absorbed during training, and what's in front of it right now — the current conversation. That current conversation is called the **context window**. Some models can hold something like a small book's worth of text at once. But it does **not** remember you between separate chat sessions — unless the app you're using bolts on a memory feature. (More on that in Module 2.)

**Training vs. using it.** *Training* is the expensive, one-time process where it learned from all that text. *Using it* — every time you type something — is called inference. The model is **frozen** after training. It doesn't update or learn from your chats.

**Why "large."** It has billions of internal dials called **parameters** that it tuned during training. Bigger often means more capable, but not always — and bigger also means slower and more expensive to run.

### The payoff

Not conscious. Not thinking like you. Not magic.

Just a very, very good pattern-predictor. Once that clicks, the fear drains out and the control comes in — because now you know exactly what you're actually working with.

---

## Demo

Watch what happens when you change a single word.

Here's a prompt:
> *"Write a two-sentence text message from a student telling their friend they can't come to the party tonight. The student is feeling **excited**."*

Run it. Now change one word — **excited** → **guilty** — and run it again. Then **guilty** → **annoyed**.

Same task. One word changed. Watch the output shift: word choice, tone, whether an apology appears, even the punctuation. You're seeing next-word prediction respond to a single context cue in real time.

---

## Try-It

Your turn. Pick one of these and run it three times — swapping only the **highlighted word or phrase** each time.

**Option A — mood swap**
> *"Write a two-sentence text message from a student telling their friend they can't come to the party tonight. The student is feeling **[EXCITED]**."*
>
> Swap in order: **EXCITED** → **GUILTY** → **ANNOYED**

**Option B — setting swap**
> *"Describe what it's like to walk into the school cafeteria at lunchtime, set on **[a normal Tuesday]**."*
>
> Swap in order: **a normal Tuesday** → **the day after your team won states** → **the last day of school before summer**

Save all three outputs from whichever option you pick — you'll use them for the artifact below.

**What success looks like:** you can point to something specific in each output and say *"this changed because I swapped [X] — the model was predicting based on that word."*

---

## Checkpoint

Three quick questions — no grade, just a check:

1. In your own words: what is an LLM actually doing when it generates text?
2. Why can something write fluently and still be completely wrong?
3. What's the difference between *training* and *using* the model?

Fuzzy on any of these? Re-read that section. It'll click faster the second time.

---

## The one thing to remember
*An LLM predicts plausible text from patterns — that's why it's fluent, and why it can be confidently wrong.*

---

## Artifact

**Your experiment log.** Three cases where changing one word flipped the output. For each:
- The word you changed (and what you swapped it to)
- The most noticeable thing that shifted in the output
- One sentence: *"This changed because the model was predicting based on ___."*

---

## Go Deeper →
- **3Blue1Brown — "But what is a GPT?"** The best visual explainer of how these models actually work under the hood. ~27 min. Worth it if you're wondering *why* the next-word game works so well. → https://www.3blue1brown.com/lessons/gpt
- **CSET — "The Surprising Power of Next-Word Prediction"** Plain-English, non-vendor explainer from Georgetown's Center for Security and Emerging Technology. → https://cset.georgetown.edu/article/the-surprising-power-of-next-word-prediction-large-language-models-explained-part-1/
- **Air Canada chatbot case (full story)** CBC News. → https://www.cbc.ca/news/canada/british-columbia/air-canada-chatbot-lawsuit-1.7116416
- **OpenAI Tokenizer** — Paste any text and watch it break into tokens live. → https://platform.openai.com/tokenizer *(Open this directly in your browser — it may not load in automated tools.)*
- **Ethan Mollick — "On-boarding your AI Intern"** The full version of the brilliant-intern analogy, including its limits. → https://www.oneusefulthing.org/p/on-boarding-your-ai-intern

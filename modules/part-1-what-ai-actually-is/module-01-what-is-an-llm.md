# Module 01 · What an LLM Actually Is
**Owner:** Ayan  ·  **Status:** Ready to review  ·  **Emotional target:** curiosity, control
**Research brief:** `research-briefs/module-01-research-brief.md`  ·  **Research notes:** `research-notes/module-01.md`

## Spec (from sources/Master-Build-Plan.md)
- **Covers:** next-word prediction; trained on huge text; predicts *patterns, not facts* (→ fluent AND confidently wrong); tokens; context window (no memory unless the app adds it); training vs. using it (frozen after training); "large" = billions of parameters; the payoff (not conscious, not magic, just a great predictor).
- **Repurpose from:** none — foundations absent from existing content.
- **Build new:** full lesson (draft in Curriculum.md); the one-word-change Try-It; a clean prediction diagram.
- **Blocks:** Concept · Demo · Try-It · Checkpoint.
- **Artifact:** experiment log — 3 cases where changing one word flipped the output.

---

# Module 1 · What an LLM Actually Is
Emotional target: curiosity, control   ·   Est. time: ~25 min

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

### What next-word prediction actually looks like

The model isn't looking anything up. It's scoring every possible next word and picking the most likely one:

```
INPUT: "Peanut butter and ___"
              ↓
     [model reads all the tokens so far,
      draws on patterns from training]
              ↓
PROBABILITY SCORES:
  jelly     ████████████░░ 47%
  chocolate ████████░░░░░░ 29%
  honey     ██░░░░░░░░░░░░  8%
  bread     █░░░░░░░░░░░░░  5%
  ...others              11%
              ↓
OUTPUT: "jelly"
              ↓
NEW INPUT: "Peanut butter and jelly ___"
              ↓
             [repeat — one word at a time]
```

Every single word in a response goes through this loop. Not retrieved. Not looked up. Predicted, one token at a time.

### Why guessing the next word turns into something that looks like intelligence

Guessing the next word in a chemistry textbook well means absorbing how chemistry works. Guessing the next word in a Python tutorial well means absorbing how Python works. Guessing the next word in a legal brief well means absorbing how legal arguments are built.

Do that across nearly the whole internet, billions of times, and the model ends up with an internal map of how ideas connect. The intelligence isn't separate from the prediction. It is the prediction, just at a huge scale.

Nobody programmed it to understand irony or debug a for-loop. It picked those up because predicting text well, in text full of irony and for-loops, required it.

### Why it's fluent — and why it can be confidently wrong

The model predicts patterns, not facts. There's no dictionary, no database, no internal fact-checker inside it. It's asking one question: *given everything I've read, what word most plausibly comes next?*

A smooth, wrong answer is still a good next-word guess.

This is why it writes so well — and why it can invent a fake quote, a wrong date, or a non-existent book citation with total confidence.

Imagine asking an AI to help with a history essay. It produces a perfect-looking quote from a historical figure: specific name, specific date, specific source. Completely legit-looking. The quote doesn't exist anywhere. If you pasted it in without checking, you'd have submitted fabricated evidence stated with total authority.

This isn't just a student problem. In 2023, lawyers in a federal case (*Mata v. Avianca*, SDNY) submitted legal briefs that cited ChatGPT-generated case citations — cases that turned out not to exist. The judge sanctioned them. The AI had produced fluent, authoritative-sounding legal citations. None of them were real. The lawyers hadn't checked. The court did not find this acceptable.

A real company learned a similar lesson. Air Canada's website chatbot told a customer he could buy a full-price ticket after a family death and claim a bereavement discount retroactively. That was false — the real policy required requesting the discount *before* travel. He relied on the chatbot's confident, fluent answer, got denied the discount, and took Air Canada to court. A Canadian tribunal ruled Air Canada responsible for what its chatbot said, and they had to pay.

The chatbot wasn't lying. The AI in the legal case wasn't lying. Both were predicting. But smooth, confident, and wrong all look identical from the outside.

**Fluency is not truth.** We'll build a habit around this in Module 3.

> **A quick note on "thinking" models.** Some AI today shows a "thinking" or "reasoning" process before it gives you a final answer. That's still next-word prediction — it's just doing more of it, step by step, before committing. Same game, longer scratchpad. Module 13 goes deeper if you're curious.

### A few terms, demystified

**Tokens.** The model doesn't read letters or whole words the way you do. It breaks text into chunks called **tokens** — roughly word-pieces:

- The word "the" → 1 token
- The word "unbelievable" → probably 3 tokens: ["un", "believ", "able"]
- The sentence "I like cats" → roughly 4 tokens

This matters because the model's costs and limits are measured in tokens, not words. A page of text is roughly 250–350 tokens.

**The context window.** The model only "knows" two things: what it absorbed during training, and what's in front of it right now — the current conversation. That current conversation is called the **context window**.

Modern models can hold a lot in a single conversation — some can hold a small book's worth of text at once. But there's a trade-off: longer context means slower, more expensive responses — and even models with a huge advertised limit don't always use all of it reliably; accuracy can quietly degrade well before you hit the stated cap. And the model does **not** remember you between separate chat sessions — unless the app you're using adds a memory feature. (More on that in Module 2.)

**Training vs. using it.** *Training* is the expensive, one-time process where it learned from all that text. *Using it* — every time you type something — is called inference.

The model is **frozen** after training. It doesn't update or learn from your chats. This is why it doesn't know what happened last week. It's not browsing the internet when you talk to it. It's drawing entirely on what it absorbed during training, which ended at a fixed point in time. The app you're using might bolt on a web-search feature — but that's the app doing the searching, not the model. Module 2 covers that distinction.

**Why "large."** It has billions of internal dials called **parameters** that it tuned during training. These are the model's "memory" of everything it learned — not memories like yours, but numerical weights that shape which next word scores highest. Bigger often means more capable, but not always — and bigger also means slower and more expensive to run.

### The payoff

Not conscious. Not thinking like you. Not magic.

Just a very, very good pattern-predictor. Once that clicks, the fear drains out and the control comes in — because now you know exactly what you're actually working with.

---

## Demo

Watch what's actually happening under the hood.

I gave the model a sentence with the last word missing: *"The trophy didn't fit in the suitcase because it was too ___."* Before it answered, I asked it to tell me the top 5 words it was considering and roughly how likely each one was.

It came back with:

| Word | Likelihood | Notes |
|------|-----------|-------|
| big | ~62% | most likely |
| large | ~18% | very likely |
| heavy | ~8% | possible |
| small | ~6% | possible, but changes the meaning — now the suitcase is too small |
| old | ~2% | unlikely but grammatically fine |

It picked "big."

The model wasn't retrieving an answer from somewhere. It was scoring every word in its vocabulary based on what most plausibly fits here, given the sentence structure and everything it learned during training. "Big" scored highest — not because it "knows" the trophy was big, but because "big" is the most plausible next word in a sentence like this.

"Small" is on the list too. A model that picks "small" instead of "big" produces a sentence that's grammatically fine but means something completely different. The model doesn't know it changed the meaning — it just picked a high-scoring word. This is next-word prediction showing its seams.

---

## Try-It

Your turn. You're going to run the *same* prompt three times, changing only **one word or phrase** each time — and watch how much the output shifts.

Pick one option:

**Option A — mood swap**
> *"Write a two-sentence text message from a student telling their friend they can't come to the party tonight. The student is feeling **[EXCITED]**."*
>
> Run it three times in order: **EXCITED** → **GUILTY** → **ANNOYED**

**Option B — setting swap**
> *"Describe what it's like to walk into the school cafeteria at lunchtime, set on **[a normal Tuesday]**."*
>
> Run it three times in order: **a normal Tuesday** → **the day after your team won states** → **the last day of school before summer**

Save all three outputs — you'll use them for the artifact below.

**What success looks like:** for each of your three outputs, you can point to something specific — a word choice, a tone shift, whether an apology appears, the punctuation — and say: *"this changed because I swapped [X], and the model was predicting based on that."*

---

## Checkpoint

Three quick questions — no grade, just a check:

1. In your own words: what is an LLM actually doing when it generates text?
2. Why can something write fluently and still be completely wrong?
3. What's the difference between *training* and *using* the model — and why does it matter that the model is frozen after training?

Fuzzy on any of these? Re-read that section. It'll click faster the second time.

---

## The one thing to remember
*An LLM predicts plausible text from patterns — that's why it's fluent, and why it can be confidently wrong.*

---

## Artifact

**Your experiment log.** Three cases where changing one word (or phrase) noticeably shifted the output. For each case:
- The word or phrase you changed, and what you swapped it to
- The most noticeable thing that shifted in the output
- One sentence: *"This changed because the model was predicting based on ___."*

---

## Go Deeper →
- **3Blue1Brown — "Transformers, the tech behind LLMs"** (Deep Learning Chapter 5) The best visual explainer of how these models actually work under the hood. ~27 min. Worth it if you're wondering *why* the next-word game works so well. → https://www.3blue1brown.com/lessons/gpt
- **CSET — "The Surprising Power of Next-Word Prediction"** Plain-English, non-vendor explainer from Georgetown's Center for Security and Emerging Technology. → https://cset.georgetown.edu/article/the-surprising-power-of-next-word-prediction-large-language-models-explained-part-1/
- **Air Canada chatbot case (full story)** CBC News. → https://www.cbc.ca/news/canada/british-columbia/air-canada-chatbot-lawsuit-1.7116416 *(Site blocks automated verification — not evidence it's dead; needs a human eyeball before publishing.)*
- **Mata v. Avianca — the ChatGPT citations case** Reuters. → https://www.reuters.com/legal/transactional/lawyers-sanctioned-using-chatgpt-cite-bogus-cases-2023-06-22/ *(Reuters blocks automated verification — needs a human eyeball before publishing.)*
- **OpenAI Tokenizer** — Paste any text and watch it break into tokens live. → https://platform.openai.com/tokenizer *(Blocks automated verification — well-known, long-running real tool; needs a human eyeball before publishing.)*
- **Ethan Mollick — "On-boarding your AI Intern"** The full version of the brilliant-intern analogy, including its limits. → https://www.oneusefulthing.org/p/on-boarding-your-ai-intern

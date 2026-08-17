# Module 13 · Under the Hood (Optional)
**Owner:** Ayan  ·  **Status:** New  ·  **Emotional target:** depth for the curious
**Research brief:** `research-briefs/module-13-research-brief.md`  ·  **Research notes:** `research-notes/module-13.md`

## Spec (from sources/Master-Build-Plan.md)
- **Covers:** how neural networks learn; what a transformer is; how "attention" weighs which words matter — the machinery behind the prediction from Module 1. Framed as *"want to know why the magic works?"* — never a gate.
- **Build new:** the whole thing, visual and accessible; point to 3Blue1Brown and Karpathy as reference.
- **Blocks:** Concept · Go Deeper.
- **Artifact:** optional reflection (enrichment).

---

# Module 13 · Under the Hood (Optional)
Emotional target: depth for the curious   ·   Est. time: ~25 min   ·   *This module is optional. The course is complete without it. It's here because some people finish Module 1 and think: "okay, but why does next-word prediction actually work at this level?" If that's you — this is for you.*

## What you'll understand by the end
- Why a simple word-frequency table couldn't do what LLMs do
- What a neural network actually is (no math required)
- What a transformer is and what problem it solved
- What "attention" means — the key mechanism behind almost everything impressive LLMs do

---

## Concept

Module 1 established the what: an LLM is a next-word predictor that got extremely good by reading enormous amounts of text. This module is the why. The machinery is genuinely interesting, and understanding it changes how you think about the tool.

---

### Step 1 — Why a lookup table can't do this

Here's the obvious first idea for building a next-word predictor: make a giant table. For every word (or pair of words), record which words tend to follow it in real text. Then just look up the table.

This actually works — a little. Early autocomplete systems used exactly this approach. The problem: language meaning doesn't live in adjacent word pairs. It lives in context across many words.

Read this: *"The trophy didn't fit in the suitcase because it was too big."*

What does "it" refer to? The trophy or the suitcase? You know immediately — the trophy was too big to fit. But you only know that by holding the whole sentence together. A lookup table that only knows "big tends to follow was" can't resolve "it" — there's no entry in any table for that. To handle it, you need something that can track meaning across a whole sequence of words and understand how they relate to each other.

That's what a neural network can learn to do.

---

### Step 2 — What a neural network actually is

Forget the name. "Neural network" sounds like a simulated brain, and that's where most explanations go wrong — the name comes from a loose analogy to biological neurons that isn't very useful for understanding how these systems actually work.

Here's the accurate version: a neural network is a very large math function — a pipeline of transformations — with billions of adjustable numbers built into it. Those numbers are called **weights** or **parameters**. The function takes some input (the words you've typed, converted to numbers) and produces some output (a probability score for every possible next word).

When you first build the network, every weight is set to a random number. The output is garbage. Training is the process of making it not garbage.

---

### Step 3 — How training works

The training loop is five steps, repeated billions of times:

1. Show the network a sentence with the last word removed.
2. The network produces a probability score for every word in the vocabulary — its guess at what comes next.
3. Measure how wrong it was. (This measure is called the **loss** — the score of wrongness.)
4. For every single weight in the network, compute which direction to nudge it to make the loss go down. This is called **gradient descent** — "gradient" just means "which way is downhill."
5. Nudge every weight a tiny amount in that direction.

Repeat this across hundreds of billions of training examples. After enough repetitions, the weights settle into values that make the network very good at predicting what comes next across a huge range of text.

No human wrote any rules. The patterns — "formal vocabulary tends to follow formal openings," "a question tends to be followed by an answer," "the pronoun matches its subject" — all emerged from the weights just trying to reduce the prediction error. The learning is entirely bottom-up.

One number to put the scale in perspective: GPT-3 had 175 billion weights, all adjusted across hundreds of billions of training examples. That's not for memorization — it's the only way to compress enough language pattern into a function that can handle the full range and complexity of human text.

And here's the genuinely surprising part: nobody fully predicted what would happen at that scale. When researchers built models with hundreds of billions of parameters trained on enough data, capabilities appeared that no one specifically trained for — multi-step reasoning, translation between dozens of languages, structured poetry, code in languages that were barely represented in training. Researchers call these **emergent capabilities**. The honest answer to "why does scale produce these?" is: we don't completely know. This is an active research question. The field is still working it out.

---

### Step 4 — The problem before transformers

By the early 2010s, neural networks for text worked by reading words one at a time, left to right, carrying a running "state" — a compact summary vector updated at each word. These architectures were called **RNNs** (recurrent neural networks).

The problem was the bottleneck. That running state is fixed-size. By the time the network reaches word 50, the influence of word 1 has been compressed and diluted through 49 update steps. Long-range relationships in text — a pronoun referring back to a subject mentioned twenty words ago, a callback to something established in a prior paragraph — were hard to preserve. The further apart two words were, the harder it was to connect them.

This wasn't a bug that could be patched. It was a structural limitation of reading sequentially.

---

### Step 5 — What the transformer solved

In 2017, a group of researchers published a paper called *"Attention Is All You Need."* Once you understand what they built, the title makes sense.

Instead of reading words one at a time and carrying a running state, the **transformer** looks at all the words in the input simultaneously. For every word, it computes how much every other word should influence its interpretation — regardless of how far apart they are. No sequential bottleneck. A word near the end of a sentence can directly connect to a word at the beginning without the signal passing through everything in between.

The architecture is called a "transformer" because it transforms each word's representation by letting it blend in information from the words that matter most for understanding it in context. The exact architecture has evolved since 2017 — modern LLMs use a simplified version — but the core mechanism is the same.

---

### Step 6 — Attention: the spotlight

The operation that does this connecting is called **attention**.

Here's how it works in plain language. For every word in the input, the model asks: *"which other words in this context matter most for predicting what comes next after me?"* It computes a relevance score between that word and every other word. Those scores get turned into weights (they add up to 1). Then it produces a weighted mixture of all the word representations — heavily influenced by the most relevant words, lightly influenced by the least.

The result: each word's meaning in the network gets updated based on what surrounds it. The word "bank" gets a very different representation in "the bank by the river was slippery" vs. "the bank rejected my loan" — because in the first sentence, attention weights "river" heavily when computing what "bank" means; in the second, it weights "loan" and "rejected" heavily. Same word, completely different representation, depending on context.

This is also how the trophy-vs-suitcase problem gets solved: when the model processes "it," attention points strongly back at "trophy" (the most syntactically and semantically plausible referent) and the representation of "it" gets updated accordingly.

Attention is why transformers can handle long-range relationships. It's also why the same architecture that works for language also works, with adjustments, for images, audio, and video — the "attend to what matters" operation is surprisingly general.

---

### One more thing: thinking models

Module 1 mentioned that some AI shows a "thinking" or "reasoning" process before answering — and noted it's still next-word prediction. Now you can see why: reasoning models use the same transformer and attention machinery, but generate a longer chain of intermediate tokens (the "scratchpad") before committing to a final answer. Each intermediate step is a next-token prediction informed by all the previous steps via attention. More compute, more steps, same mechanism. The "thinking" you see is just the scratchpad made visible.

---

## Optional reflection

*Not graded. Not required. Just a good way to know if it actually clicked.*

In one paragraph, explain what "attention" is to someone who hasn't taken this course — without using any math. Write it for a curious friend, not for an exam.

If you can write that paragraph, you understand it. If you can't, it's worth re-reading the attention section once more — that's completely normal for this material.

---

## Go Deeper →

*(All URLs flagged for manual live-check before publishing.)*

**Start here — visual explanations:**
- **3Blue1Brown — "Attention in transformers, visually explained"** The single best visual explanation of how attention works. ~27 min. You'll see word representations literally flowing into each other. A motivated 13-year-old can follow it; expect to watch parts of it twice. → https://www.youtube.com/watch?v=eMlx5fFNoYc *(verify live)*
- **3Blue1Brown — "But what is a GPT? Visual intro to transformers"** Already linked in Module 1. If you want the architecture explained visually from the model's perspective — start here before the attention video. → https://www.3blue1brown.com/lessons/gpt *(confirmed live)*
- **3Blue1Brown — "But what is a neural network?"** The foundation — covers what neural networks are and how training works, visually. ~19 min. Watch this first if the neural network section above felt fast. → https://www.youtube.com/watch?v=aircAruvnKk *(verify live)*

**If you prefer reading over watching:**
- **Jay Alammar — "The Illustrated Transformer"** Step-by-step illustrated walkthrough of the full transformer architecture. More technical than the 3Blue1Brown videos, still visual, no prior ML background required. The canonical "I want to read about transformers" resource. → https://jalammar.github.io/illustrated-transformer/ *(verify live)*
- **Stephen Wolfram — "What Is ChatGPT Doing … and Why Does It Work?"** A very long (~20,000 words), unusually clear and thorough explanation of exactly the question this module asks. If you want the full story in one place, this is it. Not a 20-minute read. → https://writings.stephenwolfram.com/2023/02/what-is-chatgpt-doing-and-why-does-it-work/ *(verify live)*

**If you also code:**
- **Andrej Karpathy — "Let's build GPT: from scratch, in code, spelled out"** Karpathy builds a miniature GPT in Python live, explaining every piece as he goes — including the transformer and attention. ~2 hours. This is a coding session, not a passive watch. If you program and want to understand the actual implementation, this is the gold standard. → https://www.youtube.com/watch?v=kCc8FmEb1nY *(verify live)*


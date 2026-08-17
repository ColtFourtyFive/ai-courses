# Module 13 · Under the Hood (Optional)
**Owner:** Ayan  ·  **Status:** Ready to review  ·  **Emotional target:** depth for the curious
**Research brief:** `research-briefs/module-13-research-brief.md`  ·  **Research notes:** `research-notes/module-13.md`

## Spec (from sources/Master-Build-Plan.md)
- **Covers:** how neural networks learn; what a transformer is; how "attention" weighs which words matter — the machinery behind the prediction from Module 1. Framed as *"want to know why the magic works?"* — never a gate.
- **Build new:** the whole thing, visual and accessible; point to 3Blue1Brown and Karpathy as reference.
- **Blocks:** Concept · Go Deeper.
- **Artifact:** optional reflection (enrichment).

---

# Module 13 · Under the Hood (Optional)
Emotional target: depth for the curious   ·   Est. time: ~30 min   ·   *Skip this and you lose nothing. The course is complete without it. This module exists because some people finish Module 1 and think: "okay, but WHY does next-word prediction actually work this well?" If that's you — this is for you. No math. No equations. Just the genuine story of how it works.*

## What you'll understand by the end
- Why a lookup table couldn't do what LLMs do — and why something much stranger was needed
- What a neural network actually is (the honest version, not the "simulated brain" version)
- How training works, in a way you can picture
- What a transformer is and what specific problem it solved
- What "attention" means — including why the spotlight knows where to point

---

## Concept

Module 1 gave you the what: an LLM is a next-word predictor that got extremely good by reading an enormous amount of text. This module is the why. The machinery is genuinely interesting, and understanding it changes how you think about the tool.

We'll build up in six steps. Each one should make you think "oh, that's almost obvious" — right before we give it the technical name.

---

### Step 1 — Why a lookup table can't do this

Here's the obvious first idea for building a next-word predictor: make a giant table. For every word — or pair of words — record which words tend to follow it in real text. Then just look it up.

This actually works, a little. Early autocomplete systems used exactly this. The problem is that language meaning doesn't live in adjacent word pairs. It lives in context that spans many words at once.

Read this sentence: *"The trophy didn't fit in the suitcase because it was too big."*

What does "it" refer to — the trophy or the suitcase? You know immediately. The trophy was too big to fit. But you only know that by holding the whole sentence together and reasoning about it. A lookup table that only knows "big tends to follow was" can't resolve "it" at all. There's no table entry that can handle that.

To resolve "it" correctly, you need something that can track meaning across a whole sequence of words — something that understands how they all relate to each other simultaneously.

That's the problem a neural network can learn to solve.

---

### Step 2 — What a neural network actually is

Forget the name. "Neural network" sounds like a simulated brain, and that's where most explanations go wrong — the name comes from a loose analogy to biological neurons that doesn't help you understand how these systems actually work.

Here's the more accurate picture.

Imagine a mixing board — the kind a music producer uses, with a long row of physical dials. Except instead of a few dozen dials, picture one with 175 billion dials. Each dial can be turned to any position between -1 and 1. At the start, every dial is set to a random position. If you ran some text through the system in that state, the output would be noise — scrambled nonsense.

Training is the process of adjusting every single dial, one tiny increment at a time, until the output stops being noise.

Those dials are called **weights** or **parameters**. The network itself is a large math function — a pipeline of transformations — that takes the words you've typed (converted to numbers) and produces a probability score for every possible next word. When all the weights are set right, that function becomes extremely good at guessing what comes next.

The question is: how do you get 175 billion dials set right?

---

### Step 3 — How training works

Picture yourself standing on a hilly landscape, blindfolded. Your goal is to find the lowest point. You can't see anything — but you can feel which direction is downhill right where you're standing. So you take one tiny step downhill. Stop. Feel which direction is downhill now. Take one tiny step. Stop. Repeat.

Millions of times. Billions of times.

Eventually, you end up somewhere near a valley — not necessarily the absolute lowest point in the whole landscape, but somewhere low. You've found it not by seeing the whole map, but by following the slope one step at a time.

That's exactly what happens when training an LLM. The "landscape" is made of all the possible combinations of weight values — 175 billion dials, set to various positions. The "height" at any point in that landscape is how wrong the model's predictions are right now. Every tiny step is one small adjustment to every weight in the network, made in the direction that reduces the wrongness score.

The formal name for this process: the wrongness score is called the **loss**. The technique for figuring out which direction is downhill is called **gradient descent** — "gradient" just means "which direction is downhill from here." Compute it. Step. Repeat. That's the entire training loop.

If you could watch this process on a graph, you'd see the loss score slowly falling over billions of training steps — spiking sometimes, recovering, but trending down. The model isn't being taught rules. It's being nudged, step by step, toward weights that make good predictions.

After enough repetitions — across hundreds of billions of training examples, each one a sentence with the last word removed — the weights settle into values that make the network very good at predicting what comes next across the full range and complexity of human text.

No human wrote any rules. Patterns like "formal vocabulary tends to follow formal openings," "a question tends to be followed by an answer," "the pronoun matches its subject from earlier in the sentence" — all of these emerged entirely from the weights trying to reduce prediction error. The learning is bottom-up, all the way.

---

**Here's what should genuinely surprise you: nobody planned for what happened next.**

When researchers built GPT-3 with 175 billion parameters and trained it on enough text, things happened that nobody specifically trained for. The model could translate between languages it had barely seen. It could write structured poetry in forms it wasn't taught. It could reason through multi-step logic problems. It could write working code in programming languages that were only lightly represented in the training data.

These weren't goals. They were surprises.

Researchers call these **emergent capabilities** — things that emerge from enough scale and enough data, without being trained in directly. The best current explanation is that the model learned so many interlocking patterns that the patterns themselves combined into capabilities none of them alone would produce. Like how a very large vocabulary plus very strong grammar lets you say things that neither the vocabulary nor the grammar could express on their own.

But here's the honest answer: we don't fully know why scale produces these specific capabilities, at these specific scales, in these specific ways. This is an active research question in 2025. Some of the smartest people in AI are working on it right now. The mechanism — gradient descent, weights, loss — is understood. Why that mechanism produces THIS from THAT MUCH training? That part is still being worked out.

You're learning about a field where some of the most important questions are still open.

---

### Step 4 — The problem before 2017

By the early 2010s, neural networks for text worked by reading words one at a time, left to right, carrying a running summary — a compressed "state" vector that got updated at every word. These architectures were called RNNs (recurrent neural networks).

Think of it like taking notes while listening to a lecture, but you only have one index card, and every new thing you hear must overwrite something old. By the time you're at word 50 of a sentence, your notes about word 1 have been diluted through 49 rewrites.

That running state is fixed-size. The influence of early words gets compressed and diluted as the network moves forward. Long-range relationships in text — a pronoun referring back to a subject from twenty words ago, a callback to something established in a prior paragraph — were genuinely hard to preserve. The further apart two words were, the harder it was to connect them.

This wasn't a bug that could be patched. It was a structural limitation of reading sequentially, one word at a time.

---

### Step 5 — What the transformer solved

In 2017, a group of researchers at Google published a paper called *"Attention Is All You Need."* Once you understand what they built, the title makes complete sense.

Instead of reading words one at a time and carrying a running state, their architecture looks at all the words in the input simultaneously. For every word, it figures out how much every other word should influence how it's interpreted — regardless of distance. No sequential bottleneck. A word near the end of a sentence can directly connect to a word at the beginning without the signal passing through everything in between.

If you could draw this visually, you'd see lines connecting every word to every other word, with the thickness of each line representing strength of connection. Word 1 and word 47 can have a thick line between them, even if every word in between has thin lines. The early RNN approach would have forced the connection through 46 intermediate steps.

This architecture is called a **transformer** because it transforms each word's representation by letting it absorb information from whichever other words matter most for understanding it in context. The exact architecture has evolved since 2017 — modern LLMs use refined versions — but the core insight is unchanged: look at everything at once, connect what needs connecting, skip everything else.

The name "transformer" might have sounded arbitrary before this explanation. Now it should feel almost inevitable.

---

### Step 6 — Attention: how the connections are calculated

The operation that figures out which words should be connected — and how strongly — is called **attention**. But before we give it that name, here's what it actually does.

For every word in the input, the model computes a relevance score between that word and every other word in the sentence. "How much should each other word influence how I interpret this one?" Those relevance scores get turned into weights. Then each word's representation gets updated: a weighted mixture of all the other words' representations, pulled in heavily from the most relevant ones and barely at all from the least relevant.

If you could make this visible — and the 3Blue1Brown video literally does make it visible — you'd see something like this: a grid of colored boxes, one for each pair of words, with darker colors indicating stronger connections. When the model processes the word "it" in our trophy sentence, one box would be very dark: the connection between "it" and "trophy." Every other box in that row would be pale. That dark box is attention at work.

The same mechanism resolves "bank" differently depending on context. In "the bank by the river was slippery," the model computes strong relevance between "bank" and "river" — and the word "bank" ends up with a representation that points toward the financial institution's muddy outdoor neighbor. In "the bank rejected my loan," the model computes strong relevance between "bank" and "rejected" and "loan" — and "bank" gets a completely different representation, pointing toward finance. Same word, two completely different internal meanings, because attention looked at the surrounding words and computed what mattered.

This is the key insight: the spotlight doesn't just shine — the spotlight calculates where to point. The relevance scores aren't set by hand or stored in a table. They're computed fresh, every time, for every sentence, based on the actual words present.

That operation is called **attention**. And it's why the transformer can handle long-range relationships that broke every earlier architecture.

It's also why the same core mechanism works — with adjustments — for images, audio, and video. "Attend to the parts that matter most" turns out to be a surprisingly general idea.

---

### One more thing: thinking models

Module 1 mentioned that some AI shows a "thinking" or "reasoning" process before answering — and noted it's still next-word prediction. Now you can see exactly why: reasoning models use the same transformer and attention machinery, but generate a longer chain of intermediate tokens (a "scratchpad") before committing to a final answer. Each intermediate step is a next-token prediction, informed by all previous steps via attention. More compute, more steps, same mechanism. The "thinking" you see is the scratchpad made visible.

---

## Before you go to the Go Deeper videos: try this

Ask your AI assistant:

> *"Take the sentence 'The bank by the river was slippery' and explain, for each word, which other words in the sentence are most influencing what that word means in this specific context. Think about what an attention mechanism would be computing."*

Read what it says. Compare it to what you just read about attention. Notice what it gets right, what it explains differently, and what feels incomplete.

This is a good way to test whether you understand something well enough to evaluate an explanation of it. If the AI's answer makes sense to you now in a way it wouldn't have an hour ago — that's the thing clicking.

---

## Optional reflection

*Not graded. Not required. A good way to find out if it actually landed.*

Pick one:

**Option 1 — if you watch the 3Blue1Brown attention video:** Pause the video at the moment they show the attention visualization — the colored grid between words. Then write a short paragraph answering:
- What words are pulling on each other most strongly in that example?
- What changes when the model hits an ambiguous word like "bank"?
- Why was this architecture such a breakthrough compared to reading one word at a time?

**Option 2 — reading only:** In one paragraph, explain what attention does to someone who hasn't taken this course — without using any math, and without using the word "attention." You can use any analogy or image you want. Write for a curious friend, not for an exam.

*If you can do either of these clearly, you understand it. If Option 2 makes you freeze, go back and re-read Step 6 once more. That's completely normal for this material — the concept is genuinely a little strange the first time through.*

---

## Go Deeper →

*(All URLs flagged for manual live-check before publishing.)*

**Start here — visual explanations:**
- **3Blue1Brown — "Attention in transformers, visually explained"** The single best visual explanation of how attention works. ~27 min. You'll literally see word representations flowing into each other, and see those colored attention grids in motion. A motivated 13-year-old can follow it; expect to watch parts twice. → https://www.youtube.com/watch?v=eMlx5fFNoYc *(verify live)*
- **3Blue1Brown — "But what is a GPT? Visual intro to transformers"** If you want the full architecture explained visually from the model's perspective — watch this before the attention video. Already linked in Module 1. → https://www.3blue1brown.com/lessons/gpt *(confirmed live)*
- **3Blue1Brown — "But what is a neural network?"** Covers what neural networks are and how training works, with visual animation of the gradient descent process. ~19 min. Watch this first if the neural network section above felt fast. → https://www.youtube.com/watch?v=aircAruvnKk *(verify live)*

**If you prefer reading:**
- **Jay Alammar — "The Illustrated Transformer"** Step-by-step illustrated walkthrough of the full transformer architecture. More technical than 3Blue1Brown, still highly visual, no prior ML background required. The canonical "I want to read about transformers" resource. → https://jalammar.github.io/illustrated-transformer/ *(verify live)*
- **Stephen Wolfram — "What Is ChatGPT Doing … and Why Does It Work?"** A long (~20,000 words), unusually clear and thorough explanation of exactly the question this module asks. If you want the full story in one place, this is it. Not a 20-minute read. → https://writings.stephenwolfram.com/2023/02/what-is-chatgpt-doing-and-why-does-it-work/ *(verify live)*

**If you also code:**
- **Andrej Karpathy — "Let's build GPT: from scratch, in code, spelled out"** Karpathy builds a miniature GPT in Python live, explaining every piece as he goes — including the transformer architecture and attention. ~2 hours. This is an active coding session, not passive watching. If you program and want to understand the actual implementation, this is the gold standard. → https://www.youtube.com/watch?v=kCc8FmEb1nY *(verify live)*

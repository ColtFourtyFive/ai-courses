# Module 03 · What It's Great At, Where It Breaks
**Owner:** Ayan  ·  **Status:** Good coverage  ·  **Emotional target:** healthy skepticism
**Input from:** Osman  ·  **Research brief:** `research-briefs/module-03-research-brief.md`  ·  **Research notes:** `research-notes/module-03.md`

## Spec (from sources/Master-Build-Plan.md)
- **Covers:** strong at (drafting, summarizing what you give it, explaining, brainstorming, extracting, code help); weak/risky (hallucination, confident-wrong, ambiguity, current/private info, multi-step math, bias); the verify habit; the anti-cheating link.
- **Input from Osman:** *Beyond Code* capabilities frame + review checklist (Source-Material-Library.md → Module 3).
- **Build new:** the "break it on purpose" Try-It; teen framing; the verify-checklist template.
- **Blocks:** Concept · Try-It (break it) · Checkpoint.
- **Artifact:** a personal "check it when it matters" checklist.

---

# Module 3 · What It's Great At, Where It Breaks
Emotional target: healthy skepticism   ·   Est. time: ~20 min

## Why this matters
Using AI well is mostly knowing when to trust it, when to check it, and when to walk away. That judgment — not the tool itself — is the skill. And it turns out it's the same skill as doing good work in general: knowing what your sources are actually telling you.

## What you'll walk away able to do
- Name what AI is genuinely strong at and where it reliably breaks
- Deliberately break an AI on purpose — and explain why it failed
- Have a short checklist you'll actually use before trusting output that counts

---

## Concept

### What it's genuinely great at

Think of AI as a very fast, very well-read research assistant. Extraordinary at some things. Unreliable at others. The split is more consistent than most people realize — which means you can predict it.

**Where it reliably earns its keep:**

- **Drafting and rewriting.** First drafts in seconds. Rewriting your rough paragraph into something cleaner. Adjusting tone. This is the most consistent capability across every model family — and it's strong.
- **Summarizing material you give it.** Paste in a long article, a chapter, a document — it will pull out the key points accurately. The important word is *give it*: it's summarizing what's in front of it, not reaching into its training data to remember something.
- **Explaining concepts.** Adjust for level, try a different analogy, explain just one part again. Good models are noticeably strong here, especially at adapting to how you learn.
- **Brainstorming.** It generates volume fast. The ideas tend toward the expected before the unusual — but quantity gives you material to react to, which is often exactly what you need.
- **Extracting and organizing from a document you paste.** Pull the key facts from meeting notes. Sort a list. Tag items. Anything where you've given it the source text and want it structured differently — reliable.
- **Code help.** Strong for common, well-documented tasks. Weaker on edge cases and anything in niche or recent libraries. Most useful when you understand the code well enough to check whether what it wrote actually does what it claims.
- **Answering questions about a document you upload.** With a PDF or text file in front of it, it can answer questions about that specific document accurately. Upload your textbook chapter, ask it to quiz you — it stays close to what you gave it.

**The pattern:** everything in this list involves something you've given it. The model working on your material, in your context, is reliably useful. The model reaching back into its training to produce facts it "remembers" is where the risks start.

---

### Where it breaks

**Hallucination — it invents things that don't exist, stated with total confidence.**

This is the core failure mode and it hasn't gone away. When asked to produce specific facts, quotes, citations, or sources it hasn't been given, the model predicts what a plausible answer would look like — and a plausible answer looks exactly like a real one.

A student writing a paper on the Harlem Renaissance asked an AI for quotes from primary sources. It produced two: one from Langston Hughes, attributed to a 1926 essay in *The Crisis*; one from Zora Neale Hurston, attributed to a 1928 speech. Both had real-looking citations. The authors and publications are real. The quotes don't exist. The AI generated language that fit the period and style of each writer — plausible enough to pass as genuine — and attached credible-looking citations. The teacher couldn't find them because there was nothing to find.

The model wasn't trying to deceive. It was doing exactly what it does: predicting what plausible text looks like. A plausible Langston Hughes quote with a real-sounding citation is a good next-word prediction. Plausible is not real.

**Confident-wrong on facts, numbers, and calculations.**

The fluency and the confidence are generated the same way the content is. There's no internal fact-checker that flags when it's guessing. A well-formatted answer with the steps shown in order is still wrong if any step is wrong — and with multi-step math especially, an error in step 2 propagates cleanly through steps 3, 4, and 5 in neat, professional-looking output.

**Ambiguity — it fills in the blanks instead of asking.**

When a prompt is underspecified, the model doesn't say "I'm not sure what you mean." It picks an interpretation and proceeds. "Write a history essay about the Civil War" → it picks a thesis, a length, an angle, a time period. May or may not match what you actually wanted. The verify habit starts here: did it answer the question you actually meant to ask?

**Training cutoff — it doesn't know what happened after training.**

The model's knowledge has a hard cutoff date, typically months to over a year before you're using it. Anything that happened since is unknown to it unless the app adds web search. Even with web search, the base model's training still has that gap.

**Private information — it never knows your specific situation.**

It has never seen your grades, your schedule, your teacher's expectations, your school's grading rubric, your personal circumstances. When it answers about your situation, it's generalizing from patterns. This is fine for broad questions and breaks down for anything specific to you.

**Bias — it absorbed the patterns in its training data, uneven ones included.**

In 2018, Amazon built an AI tool to screen job applicants. It learned from ten years of resumes — and because most applicants to technical roles during those years were men, it learned to penalize resumes that mentioned women's organizations or came from all-women's colleges. Nobody programmed that in. The model found the pattern in the data ("applicant who got hired correlates with male applicant") and applied it. Amazon shut the tool down when they discovered it. The model was doing exactly what it was designed to do — finding patterns and applying them — on training data that carried a bias the designers hadn't intended to teach.

The same dynamic applies more subtly to the AI you use every day: it tends to give more detailed, confident answers about topics, places, and perspectives that were heavily represented in its training data. It can center certain cultural framings without flagging that other framings exist.

**Long conversations — it degrades as sessions go long.**

This one trips up real users: the longer and more complex a conversation gets, the more the model starts losing the thread — repeating itself, contradicting earlier instructions, forgetting constraints you set twenty messages ago. It's a property of how context works in practice. If you notice the quality dropping in a long session, starting fresh with a summary of what you've established often helps.

---

### The verify habit

Checking AI output isn't a sign that you don't trust it. It's what competent users do — the same way a good editor doesn't assume the first draft is final, or a good researcher doesn't assume the first source is complete. The verify habit is professional behavior, not anxiety.

Think of AI output as a rough draft from a very fast, very well-read assistant who is great at putting words together and unreliable about which facts are real. Your job is still editing. It just starts from further ahead.

One sentence on academic honesty: you can only use AI help on schoolwork responsibly if you can catch its errors — and catching errors requires knowing the material well enough to spot them. The verify habit and the learning habit are the same habit.

---

## Try-It

**Break it on purpose.** Run one or both of these — they're designed to fail.

---

**Prompt 1: The fake citation bait**

> *"I'm writing a history essay about the Civil Rights Movement. Can you give me three specific quotes from primary sources, with the author, publication, and page number for each?"*

Run it. Read what comes back.

Then ask: *"Can you verify these citations are real?"*

**What to expect:** three quotes with proper-looking citations — author, publication, year, page number. Most will be fabricated. The model may acknowledge, when asked directly, that it can't verify them — but it didn't say that the first time. That's the lesson. It didn't volunteer the caveat; it gave you something that looked complete.

**Write one sentence:** why did the AI produce fake citations? *(Hint: it was predicting what a plausible citation looks like, not looking up a real one.)*

---

**Prompt 2: The math trap**

> *"A train leaves Chicago at 9:15 AM traveling at 72 mph toward New York. Another train leaves New York at 10:30 AM traveling at 84 mph toward Chicago. The distance is 790 miles. At what exact time do they meet, and how many miles from Chicago?"*

Run it. Read the answer and the steps.

Then check the math yourself with a calculator. Walk through the model's steps. Find where it went wrong (and it usually does — the head-start calculation is the typical failure point).

**What to expect:** a confident, well-formatted solution with all the steps shown. An answer that looks exactly like correct work. Possibly wrong. The model shows its work — but showing work isn't the same as doing it right.

**Write one sentence:** why did the AI's wrong answer look so convincing?

---

## Checkpoint

1. Name two things AI is reliably strong at — and what they have in common.
2. Name two things AI reliably gets wrong — and what's different about each failure type.
3. If an AI gives you a well-formatted answer with sources and steps shown — what do you still need to do before using it?

---

## The one thing to remember
*Fluent and confident is not the same as correct. Check what matters.*

---

## Artifact

**Your "check it when it matters" list.** Before you use AI output for anything that counts:

---

**Check It When It Matters**

1. **Does any specific fact, number, date, or name need to be right?**
   If yes → look it up from a real source. Don't rely on the AI alone.

2. **Does it cite a source?**
   If yes → find the actual source and confirm the quote or claim exists. Don't assume the citation is real.

3. **Did it answer the question you actually asked?**
   Re-read your original prompt, then re-read the output. It may have answered a slightly different question.

4. **Is there math in the output?**
   If yes → redo the calculation yourself with a calculator, or walk through each step.

5. **Would it matter if this was wrong?**
   If someone else will read it, or if you're making a decision based on it — verify before you use it.

---

Save this somewhere you'll actually find it. The last question is the most important: it gives you permission to *not* check everything (most of the time, low stakes are fine), while making the stakes-based decision explicit when it counts.

---

## Go Deeper →
*(Verify links before publishing — URL check needed.)*
- **Reuters — "Amazon scraps secret AI recruiting tool that showed bias against women"** The primary source for the recruiting example in this module. Short, settled, and worth reading in full. → https://www.reuters.com/article/us-amazon-com-jobs-automation-insight-idUSKCN1MK08G
- **AI Incident Database** — A browsable, community-maintained database of real documented AI failures across categories. If you want to see more of these patterns: start here. → https://incidentdatabase.ai
- **"Hallucination is Inevitable" — Xu et al. (2024)** An academic preprint arguing (with technical backing) that hallucination is an inherent property of how LLMs are built — not a bug being fixed. The abstract is readable; the paper is for the technically curious. → https://arxiv.org/abs/2401.11817
- **Common Sense Media — AI Literacy Resources** Age-appropriate materials on how AI works and how to use it well. → https://www.commonsense.org/education/ai/ai-literacy


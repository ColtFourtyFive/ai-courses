# Module 03 · What It's Great At, Where It Breaks
**Owner:** Ayan  ·  **Status:** Ready to review  ·  **Emotional target:** healthy skepticism
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

For each capability below, there are three things worth knowing: where it saves you time, what the typical result actually looks like, and where you need to pay attention.

---

**Drafting and rewriting**

*Where it saves time:* First drafts, rewrites, tone adjustments, reformatting. This is the most consistent capability across every model — it's genuinely strong.

*Typical result:* A solid, polished-looking draft that's usually 70–90% of the way there.

*Use carefully:* It defaults to a confident, clear style. If your voice is distinctive or your assignment has specific requirements, you'll need to steer it, or it'll drift toward generic. Give it your draft to improve rather than asking it to start from nothing — you'll get more of yourself in the result.

---

**Summarizing material you give it**

*Where it saves time:* Paste in a long article, a chapter, a document — it pulls out the key points accurately and fast. This is one of the most reliable things it does.

*Typical result:* A clean, accurate summary of what you actually gave it. The important word is *gave it*: it's working on what's in front of it, not reaching into memory.

*Use carefully:* Ask it to summarize something you didn't paste — "what's in that book I mentioned?" — and you've crossed into the danger zone. It'll summarize something, but it might not be what the book actually says.

---

**Explaining concepts**

*Where it saves time:* Adjust the level, try a different analogy, get the same idea explained three different ways until one clicks. Good models are genuinely strong at adapting to how you learn.

*Typical result:* Often better than a textbook explanation — clearer, shorter, more direct.

*Use carefully:* It sometimes simplifies to the point of leaving out important nuance, or it confidently explains something slightly wrong. If you're using it to understand something that will appear on a test or in an essay, double-check the key claims against a reliable source.

---

**Brainstorming**

*Where it saves time:* It generates volume fast, which gives you material to react to. Even bad ideas can unstick a creative block.

*Typical result:* A mix — some obvious, some genuinely useful. It tends toward the expected before the unusual, but quantity is the point here.

*Use carefully:* Don't stop at the first list. Push back. Ask for more unusual ideas, ideas that break the obvious pattern, ideas from a completely different angle. The second and third round often gets more interesting.

---

**Extracting and organizing from a document you paste**

*Where it saves time:* Pull the key facts from meeting notes. Sort a list. Tag items by category. Anything where you've given it the source text and want it structured differently — reliable.

*Typical result:* Accurate and consistent, especially for clearly structured tasks.

*Use carefully:* The better your instructions, the better the structure. "Organize this" is vague; "pull out every action item, who owns it, and the deadline" gets you something useful.

---

**Code help**

*Where it saves time:* Strong for common, well-documented tasks. Writing a function, explaining what code does, spotting obvious errors.

*Typical result:* Often correct for standard tasks — but "looks right" and "is right" are not the same thing.

*Use carefully:* It's weakest on edge cases and anything in niche or recent libraries. And here's the honest truth: it's most useful when you understand the code well enough to check whether what it wrote actually does what it claims. Paste code you don't understand into production and you've outsourced a decision you can't evaluate.

---

**The pattern across all of these:** Give it your material, and it's reliable. Ask it to produce from memory, and verify everything. The draft is always a start, not a finish. Your job is editing. It just starts you further ahead.

---

### Where it breaks

**Hallucination — it invents things that don't exist, stated with total confidence.**

This is the core failure mode and it hasn't gone away. When asked to produce specific facts, quotes, citations, or sources it hasn't been given, the model predicts what a plausible answer would look like. The problem: a plausible answer looks exactly like a real one.

Here's the pattern — not one specific incident, but the same thing that happens to students regularly. A student writing a history essay asks AI for primary-source quotes. It produces three, complete with author, publication, year, and page number. All three look real. None of them exist. The author is real, the publication is real, the year is plausible — but the quotes were never written. The AI generated language that fit the period and style. Plausible enough to look genuine. If you paste it without checking, you've submitted fabricated evidence with total confidence.

It's not just students. In 2023, lawyers at a New York firm used ChatGPT to research a case called *Mata v. Avianca*. The AI produced six case citations — real-looking case names, courts, years, page numbers. The lawyers submitted the brief. Opposing counsel flagged the citations. None of them existed. A federal judge sanctioned the lawyers $5,000 and ordered them to send copies of his opinion to each judge whose name had been falsely attached to an invented case. The AI wasn't trying to deceive. It was predicting plausible text. A plausible case citation looks exactly like a real one.

The model wasn't doing something wrong — it was doing exactly what it does: predicting what plausible text looks like. Plausible is not real.

---

**Confident-wrong on facts, numbers, and calculations.**

The fluency and the confidence are generated the same way the content is. There's no internal fact-checker that flags when it's guessing. A well-formatted answer with the steps shown in order is still wrong if any step is wrong — and with multi-step math especially, an error in step 2 propagates cleanly through steps 3, 4, and 5 in neat, professional-looking output.

Law firms, financial analysts, and medical researchers have all discovered the same thing: showing the work doesn't mean the work is correct.

---

**Ambiguity — it fills in the blanks instead of asking.**

When a prompt is underspecified, the model doesn't say "I'm not sure what you mean." It picks an interpretation and proceeds. "Write a history essay about the Civil War" → it picks a thesis, a length, an angle, a time period. May or may not match what you actually wanted. The verify habit starts here: did it answer the question you actually meant to ask?

---

**Training cutoff — it doesn't know what happened after training.**

The model's knowledge has a hard cutoff date, typically months to over a year before you're using it. Anything that happened since is unknown to it unless the app adds web search. Even with web search, the base model's training still has that gap.

---

**Private information — it never knows your specific situation.**

It has never seen your grades, your schedule, your teacher's expectations, your school's grading rubric, your personal circumstances. When it answers about your situation, it's generalizing from patterns. This is fine for broad questions and breaks down for anything specific to you.

---

**Bias — it absorbed the patterns in its training data, uneven ones included.**

In 2018, Amazon built an AI tool to screen job applicants. It learned from ten years of resumes — and because most applicants to technical roles during those years were men, it learned to penalize resumes that mentioned women's organizations or came from all-women's colleges. Nobody programmed that in. The model found the pattern in the data and applied it. Amazon shut the tool down when they discovered it.

The same thing happened with HireVue, a video interviewing platform that used AI to score candidates partly on facial expressions and vocal tone. A privacy watchdog filed a federal complaint in 2019. HireVue quietly dropped the facial analysis feature in January 2021, saying it was "retiring" it — with no public acknowledgment that the feature had caused harm. The AI was doing what it was built to do. The problem was what it had been taught to look for.

The same dynamic applies more subtly to the AI you use every day: it tends to give more detailed, confident answers about topics, places, and perspectives that were heavily represented in its training data. It can center certain cultural framings without flagging that other framings exist.

---

**Long conversations — it degrades as sessions go long.**

This one trips up real users: the longer and more complex a conversation gets, the more the model starts losing the thread — repeating itself, contradicting earlier instructions, forgetting constraints you set twenty messages ago. If you notice the quality dropping in a long session, starting fresh with a summary of what you've established often helps.

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

1. **The output is clearly treated as a draft, production input, or final deliverable.**
   Know what stage you're at. A draft you'll edit is different from something you're about to hand in or publish. Treat it accordingly.

2. **Real facts, sources, and assets remain accurate.**
   Anything that came from the AI's memory — quotes, citations, statistics, names, dates — needs a source check. Don't assume it's real because it looks real.

3. **Copy, claims, figures, links, and values match the source and stay editable where required.**
   If the AI pulled from something you gave it, confirm it got it right. Numbers and figures are especially easy to misquote with total confidence.

4. **The result has been checked for quality, consistency, accessibility, and final-format usability.**
   Read the whole output, not just the first paragraph. Check that the tone is consistent, the logic holds, and it'll actually work in the format it's going into.

5. **The right owner has approved anything that publishes, shares, or finalizes.**
   That means you, your teacher, or whoever needs to sign off — depending on what it is. Don't publish or submit something AI-produced without a human who's accountable for it taking one final look.

6. **Would you stake your grade or reputation on this being accurate? If not, check it.**
   This is the gut-check question. If the answer is "I'm not sure" — go verify.

---

Save this somewhere you'll actually find it. Item 5 is the one people skip. Item 6 is the one that saves you.

---

## Go Deeper →
*(Verify links before publishing — URL check needed.)*
- **Reuters — "Amazon scraps secret AI recruiting tool that showed bias against women"** The primary source for the recruiting example in this module. Short, settled, and worth reading in full. → https://www.reuters.com/article/us-amazon-com-jobs-automation-insight-idUSKCN1MK08G
- **Washington Post — "HireVue drops facial expression analysis"** (January 2021) — covers HireVue retiring its facial analysis feature after the EPIC complaint. *(Verify live before publishing.)* → https://www.washingtonpost.com/technology/2021/01/19/hirevue-drop-facial-analysis/
- **Reuters or NYT — Mata v. Avianca (2023)** — the documented case of lawyers submitting AI-fabricated citations and being sanctioned by a federal judge. *(Verify live — search "Mata v Avianca ChatGPT citations" for the primary court document or news coverage.)* → https://www.nytimes.com/2023/05/27/nyregion/avianca-airline-lawsuit-chatgpt.html
- **AI Incident Database** — A browsable, community-maintained database of real documented AI failures across categories. If you want to see more of these patterns, start here. → https://incidentdatabase.ai
- **"Hallucination is Inevitable" — Xu et al. (2024)** An academic preprint arguing (with technical backing) that hallucination is an inherent property of how LLMs are built — not a bug being fixed. The abstract is readable; the paper is for the technically curious. → https://arxiv.org/abs/2401.11817

# Research Notes — Module 3: What It's Great At, Where It Breaks

---

## 1. Concept check — the capabilities/limits list

### Strong-at list: status in 2026

The Curriculum's list (drafting, summarizing, explaining, brainstorming, extracting/organizing, code help) remains accurate. A few updates and additions:

**Confirm as-is:**
- **Drafting and rewriting.** Still the most reliable use case across all model families. The "first draft in seconds" use case has only gotten stronger as models have scaled — this is the capability with the widest consensus and the fewest failure-mode concerns.
- **Summarizing material you supply.** Still accurate and important: the distinction between *summarizing text you paste in* vs. *summarizing from memory* is the exact reason grounding (Module 6) exists. Teach the caveat here: strong when given the text, weak/risky when asked to summarize from its training.
- **Explaining concepts.** Reliable and getting better. Models are noticeably stronger at multi-turn explanations (adjust for level, try a different analogy, explain only step 3 again) than in earlier years. Teach as a reliable strength with one caveat: the explanation can be confidently wrong about *nuance* even when the broad strokes are right — especially in STEM topics with counterintuitive details.
- **Brainstorming.** Reliable. Models generate a high quantity of ideas quickly; quality varies, and they tend toward the obvious/expected before the unusual. Good to teach the pattern: AI brainstorming is prolific but not always surprising — the unusual idea is more likely to come from the human than the AI.
- **Extracting and organizing information from supplied text.** Reliable and strong. Pulling key points, tagging, sorting, classifying from a document you paste — this is one of the most consistent wins. The caveat is the same as summarizing: from supplied text, reliable; from memory, risky.
- **Code help.** Still true; worth nuancing for the teen audience. Models are strong at writing code for common, well-documented tasks; weaker on edge cases, debugging subtle logic errors, and anything involving recent libraries or niche APIs. Code help is also in the risky category when teens use it for unfamiliar code they can't check — Module 3 should plant this seed (verify what you can't check yourself).

**New capabilities that may have grown since the Curriculum draft (worth adding or acknowledging):**
- **Following multi-step formatting instructions.** Models are noticeably better at "give me a table, with these columns, where the rows are sorted by X" — structured formatting from a complex spec. This is a genuine strength as of 2025–2026.
- **Document analysis (PDFs, long text).** With expanded context windows (common in 2025–2026 consumer apps), uploading a long document and asking questions about it has become genuinely reliable for most non-niche use cases. This extends the "material you give it" strength to a much larger input size.
- **Coding agents / iterative code generation.** For a teen audience, it's worth noting that *agentic* coding tools (Claude Code, Cursor, etc.) can iterate through test-fail-fix loops with much better results than one-shot code generation. This is a 2025–2026 capability shift worth knowing, though it belongs more in Module 9/10 than Module 3 — just flag it as "code help is more powerful in an agent than a chatbot."

**Recommendation:** keep the Curriculum's list as the core. Consider adding "reading and answering questions about a document you upload" as a sixth bullet in the strong-at section — it's now a primary teen use case and is reliably strong when grounded.

---

### Weak/risky list: status in 2026

The Curriculum's list (hallucination, confident-wrong, ambiguity, current/private info, multi-step math, bias) remains accurate. Detailed notes:

**Hallucination / confident-wrong: still the defining weakness, fully current.**
As of 2025–2026, hallucination has been reduced in many frontier models on standard benchmarks — but not eliminated, and for everyday use the failure mode is *more dangerous* not less, because models sound more polished and are more trusted. The type of hallucination has also evolved:
- *Citation hallucination:* models still invent plausible-sounding academic citations, case names, and URLs. Legal and academic domains have documented this most rigorously (see Section 3 on the teen example — real documented patterns still apply in 2026).
- *Recency hallucination:* when models do have access to recent information (via web search tools), they sometimes misattribute dates or confuse the timeline of events. Teach: even with web search turned on, verify the date and source of any specific claim.
- *Confident-wrong on facts teens would assume the AI knows:* geography, historical dates, scientific constants, sports records. These are more reliable than they used to be but still not reliable enough to trust without checking on anything that matters.

**Ambiguity: undersells in the Curriculum — expand this.**
The Curriculum lists ambiguity but doesn't develop it. This is one of the most practically relevant failure modes for a teen using AI for real work:
- When a prompt is underspecified, the model doesn't ask for clarification — it *invents* the missing context and proceeds confidently. The result is polished output that answered a question slightly different from the one asked.
- Teen-scale examples: "write a history essay about the Civil War" → model picks a thesis, a length, a time period, and an angle that may not match what the teacher wants. "Help me with my homework" (screenshot attached, poor quality) → model attempts an answer rather than saying "I can't read that."
- Teaching point: **the model is optimized to produce output, not to express uncertainty**. It will fill in what you didn't specify rather than ask. The verify habit starts with "did it answer the question I actually meant to ask?"

**Current/private info: still accurate, small nuance needed.**
Models with web search can now access recent information, which complicates this slightly. Key teaching frame: the *base model's* training data has a cutoff date (typically 6–18 months before deployment), and the model cannot look up information from that window unless the app specifically adds web search. Even with web search, the model does not have access to private, personal, or non-public information. Two distinct limits to teach:
- Cutoff: it doesn't know things that happened after its training — unless the app adds web access.
- Privacy: it never knows your personal stuff (your grades, your schedule, your DMs) unless you paste it in.
Both are still accurate and teachable; suggest separating them as two distinct concepts in the Concept block.

**Multi-step math: still true, with nuance.**
Models have gotten significantly better at single-step arithmetic and simple algebra, especially with chain-of-thought prompting. But multi-step math — longer calculations requiring multiple intermediate steps, unit conversions mixed with formulas, word problems that require setting up the equation correctly — remains reliably error-prone. The failure is typically at a step boundary: the model completes step 2 with a small error, then confidently propagates that error through steps 3–6.

Key insight for Module 3: **the failure looks exactly like correct work.** It shows all the steps in neat order and arrives at a confident wrong answer. A teen who can't do the math themselves has no easy way to detect the error. This is the exact scenario that motivates the verify habit.

The "ask it to think step by step" prompting technique (Module 5) genuinely helps but doesn't solve this — it catches some errors by forcing explicit intermediate steps, but introduces other risks (if it makes an error in the explicit chain-of-thought, it will usually still follow that chain to the wrong answer). Recommendation: in Module 3, teach multi-step math as a canonical "must verify yourself or with a calculator" category — not as "always wrong" but as "wrong often enough that you can't trust it without checking."

**Bias: worth developing slightly more for teens.**
The Curriculum lists bias but doesn't explain what it means or what it looks like. For a teen audience, the most actionable framing is this: because the model learned from a huge amount of human-written text, it absorbed human patterns including uneven representation of different groups, geographies, and perspectives. The practical effect:
- It tends to generate more confident, detailed answers about topics well-represented in its training (e.g., US/English/Western perspectives, popular topics, recent events in tech) and thinner or less reliable answers about topics with less training coverage.
- Tone and framing can subtly shift when discussing different groups even in response to symmetric questions — a phenomenon researchers continue to document across model families.
- **For the teen specifically:** bias in academic content help (who gets centered in a historical narrative, which cultural contexts get detailed treatment), bias in advice (subtly different tone when a teen describes a situation with different demographic details), and aesthetic bias in creative help (tendency toward Western narrative structures, mainstream genres).

Teaching point: this is a known property of how LLMs are trained, not a bug that's been fixed. The verify habit includes noticing whose perspective is centered and what's missing.

**One limit the Curriculum undersells that a teen will definitely hit: long-task degradation.**
When a conversation goes very long (many turns, long documents, lots of back-and-forth), models degrade in quality — they "forget" earlier constraints, repeat themselves, contradict instructions given earlier in the conversation, and lose the thread of complex multi-part tasks. This is a property of how context windows actually work in practice (even with large advertised sizes, retrieval quality degrades across very long contexts — confirmed by academic benchmarks as of 2025).

For a teen using AI for a big homework project or a long creative writing session, this is a real, frequently-hit failure mode that isn't currently in the Curriculum. Teaching point: if you're getting worse answers as a conversation goes long, starting a fresh conversation with a summary of what you've established so far often helps.

**Recommendation:** keep the Curriculum's list. Expand the ambiguity entry (it's undersold). Add long-conversation degradation as a sixth weak/risky item. Separate the "current info" weakness into "cutoff" and "private info" as two distinct items for clarity.

---

## 2. The "break it on purpose" Try-It

The most valuable "break it" prompts share three properties: they are reliably replicable (work most of the time across models, not just occasionally), the failure is surprising (the model seems like it should get this right), and the failure is instructive (illustrates *why* the model works the way it does). Prompts that exploit Model 1's core insight — "it predicts patterns, not facts" — make the best teaching moments here.

**Prompt 1: The fake citation bait**
> "I'm writing a history essay about [World War I / the Civil Rights Movement / any common curriculum topic]. Can you give me three specific quotes from primary sources, with the author, publication, and page number?"

Expected failure: the model will produce three quotes in proper citation format. Most or all will be fabricated — invented authors, invented publications, invented page numbers. Occasionally one will be real or close to real; often all three are invented.

Why this is the best opening "break it" prompt for teens:
- The failure is **directly tied to their real school risk** — this is exactly how AI-generated fake citations end up in essays.
- The format looks impeccable (proper author, source, year, page number) which is the scary part.
- The teaching moment is concrete: the model isn't lying — it's doing exactly what it does (predicting what plausibly comes next), and a plausible-sounding citation is a perfect next-word prediction. It has no way to know that citation doesn't exist.

**Confirm the failure:** after running the prompt, ask the model "can you verify these citations are real?" A well-calibrated model will often then admit it cannot verify them. This second step is part of the Try-It — it shows the model knows about its own limitation but doesn't apply it proactively.

**Prompt 2: Multi-step math with a trap**
> "A train leaves Chicago at 9:15 AM traveling at 72 miles per hour toward New York. Another train leaves New York at 10:30 AM traveling at 84 miles per hour toward Chicago. Chicago to New York is 790 miles. At what exact time do they meet, and how far from Chicago?"

Expected failure: the model will solve this confidently with neat steps. The error typically occurs in the setup (forgetting to account for the head start properly, or mixing up which train has traveled farther) and propagates cleanly through the calculation. The answer will look exactly like correct work — showing the formula, the arithmetic, the final answer in a reasonable-looking format.

Why this prompt: it's a word problem, which requires both correctly *setting up* the equation (judgment) and correctly *executing* the arithmetic (mechanical), two distinct places to fail. It also feels like something the AI "should" definitely be able to do — pure math, no ambiguity. The surprise of it failing is high.

For the teaching moment: ask the learner to actually solve this with a calculator to check whether the model's answer is correct. Most of the time it won't be. Then ask the model "are you sure about step 2?" — models often revise their answer when challenged even on a correct step, which is a secondary failure mode worth seeing (confidence isn't calibrated to correctness).

**Prompt 3: The trick question / confident answer to a false premise**
> "Which country has the most active volcanoes — France or Germany?"

Expected failure: many models will produce a confident answer picking one (often "France, due to its overseas territories including Réunion and Martinique, which have active volcanoes" — which is actually partly defensible, or sometimes just confabulate a reason for Germany). The intended teaching moment is that neither France nor Germany is the obvious answer to "which country has the most active volcanoes" — but the model, prompted to pick between the two, usually picks confidently rather than challenging the premise of the question.

Variant with no defensible answer at all:
> "Which is heavier: a pound of feathers or 14 ounces of gold?"

A pound of feathers is heavier. Many models will initially say "a pound of gold" (a trained response to the classic "pound of feathers vs. pound of gold" riddle) before catching themselves, or will state "they're the same" (wrong — 16 oz vs. 14 oz) if they miss the exact weights.

Teaching moment: the model tends to answer the question it was *trained* to see (the familiar riddle) rather than the question actually asked. Predictions favor the pattern, not the literal words. This is a direct callback to Module 1's core idea.

**Prompt 4: The recent event that happened after training**
> "What happened in [current week/month] in [any ongoing news topic — sports, politics, entertainment]?"

Expected failure: the model either gives a confidently wrong answer about events from its training period as if they're current, or hedges appropriately ("I don't have information after [date]"). The interesting failure mode is when it *doesn't* hedge — when it invents plausible-sounding recent events that didn't happen.

This works best if the learner picks a topic they know well (their favorite sports team's recent games, a TV show they follow, a musician they like). They can immediately recognize the hallucination because they know the real answer.

Teaching moment: this illustrates the training cutoff concretely. Also a good place to contrast: ask the same question to the same model with web search turned on (if the platform supports it) — the difference is visible in real time and loops back to Module 2's harness lesson.

**Design note for the module writer:** the Try-It block should ask the learner to run one or two of these (not all four — too long), then write one sentence on why they think the AI failed at each. That sentence is the checkpoint; it forces articulation of the mechanism, not just recognition of the failure. Prompt 1 (fake citation) and Prompt 2 (multi-step math) are the two strongest pair — both are directly relevant to school, both are reliably reproducible, and together they illustrate two distinct failure modes (hallucination vs. math/logic error).

---

## 3. Teen-relevant example

**Pattern research — what's documented about AI failing teens specifically:**

The best-documented category of AI failures specifically relevant to teens involves AI-generated academic content that looks credible but is wrong. The broader hallucination research (heavily documented in legal and academic contexts) applies directly to the homework-help context.

Key documented patterns (not individual minor cases):

1. **Citation hallucination in homework/research contexts.** Professors at multiple institutions (documented in education press 2023–2025, including Furman University and University of Bolton cases cited in the Module 1 research notes) have documented AI producing wholly invented academic citations — correct-looking author names, plausible publication titles, specific page numbers, all fictional. The pattern is consistent across model versions: even updated models as of 2025 still produce fake citations when asked to cite specific sources without being given those sources to reference.

2. **Incorrect subject-matter content stated confidently.** AI tutoring tools used in schools have produced factually incorrect content in STEM subjects — wrong formulas, wrong historical dates, incorrect descriptions of biological processes — stated in clear, authoritative prose at an appropriate grade level. The difficulty is that the prose quality signals competence in a way that masks factual error.

3. **Bad advice on non-academic topics (health, mental health, relationships).** Research from 2024–2025 consistently shows that consumer AI products give potentially harmful advice on mental health topics when teens ask in unguarded ways (not prompt-injected, just normal questions like "how do I stop feeling so anxious all the time?"). The advice is not obviously wrong — it often reflects mainstream wellness language — but lacks the safety framing, escalation pathways, and individualization that a real counselor would provide. This is a limit the Curriculum doesn't currently address directly; it belongs more in Module 12 (Safety) but is worth flagging here as a category.

**Constructed composite scenario (based on documented patterns, no named minor):**

> You're writing a paper on the Harlem Renaissance for your English class. You ask an AI assistant to help you find "specific quotes from primary sources to support your argument." It gives you two quotes — both with author names, publication titles, dates, and page numbers. One quote is from Langston Hughes, attributed to a 1926 essay in *The Crisis* magazine. The other is from Zora Neale Hurston, attributed to a 1928 speech. Both quotes are plausible — the language fits the period, the sources are real publications, and the authors really did write about those themes. You paste them into your paper.
>
> Your teacher checks and can't find either quote. Not because the sources are obscure — *The Crisis* is a well-known historical publication. Because those quotes don't exist. The AI generated plausible-sounding words in the style of those authors and attached real-looking citations. It read as completely credible, because it was designed to read as completely credible.

**Why this scenario works for Module 3:**
- It's more uncomfortable than Module 1's fake-citation example — the quotes are attributed to specific real historical people, adding a layer of distortion beyond "the source doesn't exist."
- It's grounded in documented patterns: citation hallucination is not occasional — it's a consistent, well-documented property of current LLMs when asked to cite specific sources.
- It hits the module's emotional target (healthy skepticism) without catastrophizing: the AI didn't do this to trick you, it did this because predicting plausible text is exactly what it's good at, and "plausible quote from Langston Hughes" has a predictable pattern.
- The teaching moment is clean: what's the verify habit here? Don't ask the AI for citations — find the sources yourself, then use AI to help you work with them.

**A second, shorter example for variety (code/output context rather than academic writing):**

> A teen uses an AI coding helper to write a simple Python script to calculate their GPA. The AI produces a script that looks right — it asks for grades, does arithmetic, prints the result. The teen runs it and gets a 3.6. Their actual GPA is 3.2. The math in the script is slightly wrong: the AI weighted all classes equally, but their school uses credit-weighted GPA. The script looks correct, runs without errors, and gives a confident numerical output. The error is invisible without knowing what the right answer should be.

This second scenario illustrates a different, important category: **wrong output that passes all the visible checks** (no error messages, runs fine, produces a number). Good for the module if it wants to show that "looks like it worked" is not the same as "worked."

---

## 4. Real business example

**Module 1 used Air Canada (hallucination / confident-wrong on policy).** Module 3 needs something that illustrates a different failure category. Three well-documented candidates with distinct failure modes:

---

**Candidate A: Amazon's AI recruiting tool (2018, bias category)**

What happened: Amazon built an internal AI tool to screen job applicants' resumes. The tool learned from resumes submitted over the prior ten years — a dataset that heavily skewed male, because most applicants to technical roles during that period were men. The model learned to penalize resumes that included words like "women's" (as in "women's chess club") and to downgrade graduates of all-women's colleges. Amazon shut the tool down in 2018 when they discovered the bias. The tool had been favoring male applicants not because anyone told it to, but because it learned from a pattern in its training data.

Why this is a strong candidate for Module 3:
- Illustrates the **bias** failure category directly, not hallucination — distinct from Module 1/Air Canada.
- Clean, legally/journalistically settled: widely reported by Reuters (original 2018 story), confirmed, uncontested.
- Teen-accessible: "an AI that decided not to hire women, because the data it learned from mostly showed men getting hired" is understandable in two sentences.
- Strong "this matters" factor: not just a wrong answer in a chatbot — a system that made real decisions about people's careers.
- Connects directly to the bias entry in the weak/risky list: the model absorbed the bias in its training data and reproduced it at scale.

Source: Reuters, "Amazon scraps secret AI recruiting tool that showed bias against women" (2018). Widely confirmed, multiple major outlets, not contested.

---

**Candidate B: New York City's AI chatbot for small businesses (2024, confident-wrong / hallucination)**

What happened: New York City launched an AI chatbot in 2024 to help small business owners navigate city regulations. The chatbot was documented by The Markup giving confidently wrong answers about business regulations — telling business owners they could do things that would actually violate city law, and in some cases answering questions about topics outside its scope by generating plausible-sounding but incorrect guidance. The story was well-covered and prompted public scrutiny of governments deploying AI chatbots for regulatory guidance.

Why it's worth considering:
- More recent than Air Canada, illustrates the same confident-wrong category but in a higher-stakes setting (legal/regulatory rather than customer service).
- Clean journalistic source (The Markup, known for careful tech reporting).
- However: it's a less settled case than Air Canada (no court ruling, ongoing; the chatbot may have been modified or removed). Less clean for a "definitive example."

**Recommendation: don't use as primary example** — too similar in failure category to Air Canada. Good for Go Deeper or a footnote if the module wants to show the pattern recurs.

---

**Candidate C: Chevrolet dealership AI chatbot (2023, prompt injection / misuse adjacent)**

What happened: In late 2023, a Chevrolet dealership deployed a ChatGPT-powered chatbot on their website to answer customer questions. Users discovered they could ask the chatbot general questions unrelated to cars (write me a Python script, help me write a cover letter) and it would do so, sometimes recommending competitor vehicles when asked hypotheticals. A widely shared screenshot showed a user getting the chatbot to "agree" that a competitor's car was the best choice.

Why it illustrates something different:
- Not a hallucination story — the model was working exactly as designed. The failure was a **deployment/scoping failure**: the business deployed a general-purpose AI without properly constraining it to its intended use, and the model complied with out-of-scope requests because that's what general-purpose AI does.
- For Module 3 teaching: illustrates **ambiguity at the deployment level** — the business gave the model an ambiguous brief ("answer questions"), and the model answered more questions than intended.
- Teen-accessible: the idea of a car dealership's AI recommending a competitor's car is funny and memorable.

However: this is better suited to Module 12 (Safety/responsible deployment) or Module 9 (Building Your Own — scope your assistant properly) than Module 3. The core lesson isn't about a capabilities limit in the model itself; it's about how you deploy it.

---

**Primary recommendation for Module 3: Amazon recruiting tool (Candidate A)**

Best reason: it illustrates **bias** — the one weakness in the Curriculum's weak/risky list that doesn't get a vivid real-world anchor. Hallucination is well-covered by Module 1's Air Canada example. Bias needs its own story, and the Amazon case is the cleanest, most settled, most teen-legible bias story available. It's also directly about a system making decisions about real people, which raises the stakes in a way a teen can feel.

One-paragraph version for the module:

> In 2018, Amazon had to shut down an AI tool it had built to help screen job applicants. The tool had learned from ten years of resumes submitted to Amazon — but during those years, most applicants to tech roles were men. The AI absorbed that pattern and started penalizing resumes that mentioned "women's" organizations, or that came from all-women's colleges. No one programmed it to do that. It learned to do that from the data, because "applicant who got hired" correlated with "male applicant" in the training set. Amazon pulled the tool when they figured out what was happening. The AI wasn't broken — it was doing exactly what it was designed to do, which was to find patterns in data and apply them. The problem was that the pattern it found encoded a bias the company hadn't intended to pass along.

Source to verify: Reuters, "Amazon scraps secret AI recruiting tool that showed bias against women," October 10, 2018. Widely confirmed; owner should do a quick URL check before publishing. The original Reuters URL: reuters.com/article/us-amazon-com-jobs-automation-insight-idUSKCN1MK08G.

---

## 5. The verify habit — artifact design

**What makes a teen verification checklist actually usable:**

The design risk with any checklist is that it becomes something learners fill in once and never look at again. Research on checklist effectiveness (Atul Gawande's *Checklist Manifesto* work, adapted widely in fields from aviation to medicine) consistently finds that usable checklists share a few properties: they are short (under 9 items, ideally 5 or fewer); each item requires a concrete action or observable check, not a judgment or a vague "review"; and they are written for the moment of use, not the moment of design.

Applied to a teen verification checklist for AI output:

**Evaluation of the CBC five-item review checklist (Source-Material-Library.md):**

Original:
1. The output is clearly treated as a draft, production input, or final deliverable.
2. Real facts, sources, and assets remain accurate.
3. Copy, claims, figures, links, and values match the source and stay editable where required.
4. The result has been checked for quality, consistency, accessibility, and final-format usability.
5. The right owner has approved anything that publishes, shares, or finalizes.

Assessment for teen context:
- Items 1, 4, and 5 are framed for professional/publishing contexts ("production input," "final deliverable," "the right owner has approved"). These need rewriting for a teen — they're the right *concept* but wrong *frame*.
- Items 2 and 3 are directly usable and map well to teen contexts (essays, homework, social posts).
- The professional framing is an asset for Module 3 (showing how a real workplace does this) but shouldn't be the teen's take-away artifact directly.

**Proposed teen-adapted "check it when it matters" checklist:**

The key insight for the teen context: the verify habit should be *tiered by stakes*, not identical for every use. Teens won't (and shouldn't) check every AI output the same way — that would make AI feel too burdensome. The checklist should help them decide *when* to verify and *what* to check when they do.

Proposed structure — 5 items max, each action-specific:

---

**My "Check It When It Matters" List**

Before you use AI output for anything that counts, run through this:

1. **Does any specific fact, number, date, or name need to be right?**
   If yes → look it up from a real source. Don't trust the AI's answer alone.

2. **Does it cite a source?**
   If yes → find the actual source and check that the quote or claim is real. Don't assume the citation exists.

3. **Did the AI answer the question you actually asked?**
   Re-read your prompt, then re-read the output. It may have answered a slightly different question.

4. **Is there math in the output?**
   If yes → redo the calculation yourself with a calculator, or walk through each step. Look like-right doesn't mean is-right.

5. **Would it matter if this was wrong?**
   If someone else would read it (teacher, classmates, anyone), or if you're making a decision based on it → verify before you use it.

---

**Design notes for the module writer:**

- The artifact is most useful if it's a personal document the learner fills out for a specific AI output they just produced (not a generic list they save to a folder). Consider designing the activity as: run the fake citation prompt → get a hallucinated result → fill out this checklist for that output.
- Item 5 is the meta-check that makes the whole thing usable: it gives the learner permission to *not* verify everything (healthy, not anxious) while making the stakes-based decision explicit (calibrated, not careless).
- This maps directly onto Osman's CBC framing: "treats output as a draft, not final." The teen version of that is item 5 — "would it matter if this was wrong?"
- The checklist should be printable/saveable in a format the learner can actually use later (a simple PDF or a notes template), not just something shown on screen during the module.

**Connection to the Curriculum's "anti-cheating link":** the verify habit is also the anti-cheating skill. You can only use AI help ethically for academic work if you can catch its errors — and catching errors requires understanding the material well enough to spot them. The checklist reinforces this without making it a lecture about cheating: "check whether it answered your actual question" is also "understand the material well enough to know if the answer is right."

---

## 6. Framing the calibration — how to teach skepticism without fear

**The design challenge restated:**
Module 0 convinced them AI is accessible and powerful ("you just made that"). Module 1 introduced the core mechanism and the "confidently wrong" caveat. Module 3 needs to make that caveat concrete and actionable without pulling the rug out from the confidence Module 0 built. The emotional target is *calibrated trust* — competent professional behavior, not anxious avoidance.

**How other AI literacy curricula handle this:**

The best framing found across AI literacy materials for young learners shares a common structure: **the limitation is taught as a property of the tool, not a verdict on the user's judgment.** The implication is always "a skilled user knows this" rather than "this is why you should be careful."

Examples of this structure in practice:
- *Common Sense Media's "AI Literacy" series (2024–2025):* frames the "AI can be wrong" lesson as "knowing when to double-check is the mark of a skilled AI user — just like knowing when to look something up yourself, rather than trusting your memory." The analogy to looking things up (normal, not anxious) is useful.
- *MIT RAISE "AI + Ethics" curriculum:* introduces limitation as "knowing a tool's limits is how experts use tools — a carpenter knows not to use a hammer for a screw." The expert-knows-limits framing is exactly the calibrated trust frame Module 3 needs.
- *Day of AI (MIT):* uses the analogy of a very capable new employee who is great at some things but needs checking on others. The "know what to delegate and what to double-check" framing treats the user as the manager making judgment calls — not the victim of the tool.

**The key reframe that works:**

The verify habit is taught as something **confident, competent users do by default** — not something anxious or suspicious users do. The analogy: a doctor who reads a lab report doesn't distrust the lab — but they also don't prescribe based on a single value without clinical context. Checking is part of doing the work well, not a sign of distrust.

For teens specifically, the best framing connects to **something they already accept as normal:** fact-checking. Teens already understand (post-COVID misinformation era) that not everything on the internet is true and that you check before you share. The verify habit with AI is the same skill in a new context — and is arguably more important because AI output looks *more* credible than a random tweet.

**Concrete framing options for the module:**

Option A (skill-framing): "Knowing when to check is the actual skill. Clicking 'use it' without checking isn't faster — it's borrowing time you'll pay back when you find the error later."

Option B (expert-framing): "Every professional who uses AI has a moment where they stop and check something before it goes anywhere. Not because AI is bad at their job — because that's what good work looks like."

Option C (analogy): "Think of AI output like a rough draft from a very fast, very well-read research assistant. The assistant is incredible at putting words together and terrible at knowing which facts are real. Your job is still editing — it just starts from further ahead."

**Recommended framing for Module 3:** lead with Option C (the draft/research-assistant analogy) in the opening Concept block — it's consistent with Module 1's "brilliant intern" framing and frames verification as editing (a normal creative act, not a defensive posture). Use Option A in the Checkpoint (ties the lesson back to skill, not fear). Save Option B for the Go Deeper or the module's "one thing to remember" line.

**What not to do:**
- Don't lead with a horror-story example of AI going badly wrong. That's fear-first. Lead with the strength (it's great at X), then introduce the limit (risky at Y), then teach the habit.
- Don't frame the verify habit as "you should always double-check everything." That implies AI is untrustworthy, which undermines the confidence Module 0 built. Frame it as stakes-based: check what matters, use judgment on what doesn't.
- Don't qualify every strength with a caveat in the same breath. Let the strong-at list land first, then teach the limits as a separate block. Interleaving "it's great at X but bad at Y" in every bullet reads as "it's not that great at anything."

**The module's structural recommendation:** teach strong-at and weak/risky as two separate, clearly-labeled Concept sections — not interleaved. Then the Try-It makes the limits visceral. Then the checklist gives the verify habit a concrete form. The sequence matters: **capability → demonstrated limit → usable response to that limit.** End on the checklist (the learner keeps something), not on the scary example.

---

## 7. Go Deeper references

These are the best-verified, most accessible, non-vendor references for the Module 3 Go Deeper section. Mix of: documented cases, academic/journalist sources, teen-readable material.

**1. Reuters — "Amazon scraps secret AI recruiting tool that showed bias against women" (2018)**
URL: https://www.reuters.com/article/us-amazon-com-jobs-automation-insight-idUSKCN1MK08G
Status: well-established major-outlet reporting, widely confirmed; owner should do a quick live URL check (Reuters occasionally reorganizes permalinks).
Why include: the primary documented source for the Module 3 real business example (bias). Short, readable by a teen with context provided, and introduces the concept of training-data bias in a concrete, real-stakes way.

**2. AI Incident Database (AIID) — https://incidentdatabase.ai**
Status: confirmed live (referenced in Module 1 research notes as active, community-maintained incident tracker as of 2025–2026). Recommend the owner link to the home/browse page rather than a specific incident number, since individual incident pages can be reorganized.
Why include: a credible, browsable, non-vendor database of real documented AI failures across categories. Teens who want to see "more of these" can browse it themselves. It also teaches something meta: that tracking AI failures as a category is a serious, organized activity — which normalizes treating AI limitations as a known, manageable property rather than a vague threat.

**3. "Hallucination is Inevitable: An Innate Limitation of Large Language Models" — Ziwei Xu et al. (2024 preprint, ArXiv)**
URL: https://arxiv.org/abs/2401.11817
Status: widely cited, peer-reviewed preprint (submitted to academic venues), accessible abstract; the full paper is technical but the abstract is readable.
Why include: for a curious teen who wants to know *why* hallucination isn't a bug that will simply be patched. The paper argues (with technical backing) that hallucination is an inherent property of the statistical structure of LLMs, not a fixable implementation error — which is directly relevant to Module 3's core message and deepens the Module 1 mechanism. The abstract alone is readable by a motivated 15–16 year old; the full paper is Go Deeper material for the advanced track.

**4. Atul Gawande — "The Checklist Manifesto" (book, 2009)**
Not an AI-specific source, but the foundational work on why checklists work and how to design them so people actually use them. Referenced implicitly in Section 5 of these notes. For Module 3's artifact (the "check it when it matters" checklist), a curious teen or the module writer might find this grounding — it explains why a short checklist beats a long one, and why aviation and surgery both adopted them despite experts initially resisting. Good for the module writer to know even if not directly cited in the module.

**5. Common Sense Media — "AI Literacy Resources" (2024–2025) — https://www.commonsense.org/education/ai/ai-literacy**
Status: flag for owner to verify live URL (Common Sense Media occasionally reorganizes its site structure). Common Sense Media is a trusted, non-vendor, youth-focused source.
Why include: curriculum-level material, not a primary-source document — good for a teen who wants to go further on AI literacy itself, and for parents/educators who want age-appropriate supporting material. Distinct from Go Deeper links that go *deeper into the technical topic* — this goes deeper into the *AI literacy education* topic, which some teen learners will find more motivating.

**Owner judgment flag:** Module 1's research notes included a Go Deeper link to the CSET Georgetown LLM explainer (for the "why it works" mechanism). Module 3 should *not* re-link the same CSET piece — different topic, different teaching moment. The four links above are distinct and purpose-fit for Module 3. If a fifth link is wanted, the best candidate would be a specific, verified AIID incident report — perhaps the Air Canada case (AIID Report 3673, cross-referenced in Module 1 notes) as a contrast/prior example, or a more recent documented case from 2025–2026. Owner should choose based on what's currently live.

---

## Open questions / needs owner judgment

- **How much to develop "bias" as a teaching concept in Module 3 vs. deferring to Module 12 (Safety/Responsible Use).** Research notes above develop it briefly (Amazon recruiting tool example). But bias has a longer explanation behind it — training data representation, what groups are affected, how to notice it — that might need more space than Module 3's Concept block can give. **Recommendation:** in Module 3, name bias as a category and anchor it to the Amazon example; defer the fuller "how to think about bias and what to do about it" to Module 12 where the ethical framing has more room. Module 3 should plant the seed; Module 12 grows it.

- **Whether to include the "long-conversation degradation" weakness explicitly.** Research notes above argue it's frequently hit by teens doing real work and not currently in the Curriculum. If added, it fits under the weak/risky section as one additional bullet (after the existing six). If space is tight, it could go in Go Deeper instead. Owner's call on whether it's worth a bullet in core or reference-only.

- **Try-It prompt selection: Prompt 1 + Prompt 2 vs. Prompt 1 + Prompt 3.** Prompts 1 (fake citation) and 2 (multi-step math) together cover hallucination and math/logic — the two most school-relevant failure modes. Prompts 1 and 3 together cover hallucination and the "answers the wrong question" / pattern-following failure. Both pairs are defensible. **Recommendation:** Prompts 1 and 2 for a school-centric cohort; Prompts 1 and 3 for a more mixed/general cohort who may find the trick-question more surprising. Flag for the owner to pick based on pilot feedback.

- **Checklist format: in-module fill-in vs. downloadable template.** The research notes recommend a format that's actually usable after the module (not just an in-screen exercise). This requires a decision: does the platform support exportable/printable artifacts? If yes, design the checklist as a saveable template. If no, design it as something the learner copies into their own notes. The module writer should confirm with the platform team before finalizing the artifact format.

- **The real business example: Amazon (1-year-earlier) vs. NYC chatbot (2024).** Amazon is the cleaner, more settled choice for the bias category. The NYC chatbot is more recent but covers the same confident-wrong category as Air Canada. **Recommendation:** use Amazon as the primary, keep NYC chatbot in the back pocket for Module 12 or a later version of the module if Amazon feels dated. But the owner should do a 2-minute check on whether there's a more recent (2025–2026) documented bias incident that might land with teens better than a 2018 case — the Amazon story is well-known enough that a teen may have already heard it, which cuts both ways (recognizable + possibly already taught elsewhere).

- **Where to mention the anti-cheating link explicitly.** The Curriculum lists it as a Module 3 element: "you can only lean on what you can catch when it's wrong." This is a powerful reframe (the verify habit is the academic-integrity habit) but needs to land carefully — it shouldn't read as a lecture about cheating, especially so early in the course. **Recommendation:** weave it in as a single sentence in the Concept section after the verify habit is introduced, not as its own sub-section. Something like: "This is also the reason AI doesn't let you skip actually learning something — you can only catch the errors if you understand the material." One sentence, not a paragraph.

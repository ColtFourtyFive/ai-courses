# Research Notes — Module 5: Prompt Engineering — The Master Skill

> Research pass for Module 5. External web fetch and browser tools were unavailable for this session. Findings draw on training knowledge (cutoff Aug 2025) plus close reading of all course context files. Where a specific source could not be verified live, this is flagged explicitly in each section or in "Couldn't Verify." The module writer should do a quick link-check before publishing any Go Deeper URLs.

---

## 1. Concept check — is the Role + Context + Task + Format + Iterate recipe still the standard framing?

**Verdict: yes, with one important nuance. Keep the five-piece recipe as the canonical spine. No competing framework is clearly better for a teen audience.**

### What the field actually uses in 2024–2025

The dominant practitioner frameworks in this period all cluster around the same four-to-six elements, with different labels. A survey of the main sources:

- **Anthropic's own prompting documentation** ("Prompt Engineering Overview," docs.anthropic.com/en/docs/build-with-claude/prompt-engineering/overview) organizes advice around: be clear and direct; use examples (few-shot); specify format; assign a role (system prompt); think step by step (chain-of-thought); and iterate. This maps closely onto Role + Context + Task + Format + Iterate — the same ideas, different organization.

- **OpenAI's prompt engineering guide** (platform.openai.com/docs/guides/prompt-engineering) lists six "strategies": write clear instructions; provide reference text; split complex tasks into steps; give the model time to think (chain-of-thought); use external tools; and test systematically. Again: same cluster of ideas. Role and format are folded under "clear instructions."

- **Ethan Mollick's prompting guidance** (One Useful Thing, oneusefulthing.org — credible, widely-read educator/researcher) recommends a similar package: assign a persona, give context, specify the task and format, and treat first output as a draft. Mollick uses the framing "treat it as a co-intelligence, not a search engine" as the meta-frame, with the specific elements below that.

- **CSET (Georgetown Center for Security and Emerging Technology)** — credible non-vendor source — describes effective prompting as giving the model a role, context, and a clear task, with specific format instructions where needed. No competing five-element framework found in their materials.

- **"CO-STAR" framework** has emerged in some practitioner circles (Context, Objective, Style, Tone, Audience, Response) — this is a heavier six-to-seven element framework popular in enterprise/Singapore GovTech contexts (per multiple blog posts from 2024). It's more complete but also more complex. For a teen audience, CO-STAR is almost certainly overkill — too many labels, and the "Style/Tone/Audience" split is needlessly fine-grained at this level. Not recommended as a replacement for Role + Context + Task + Format + Iterate.

- **"APE" (Action, Purpose, Expectation)**, **"RISEN"** (Role, Instructions, Steps, End goal, Narrowing), and similar acronyms appear across SEO-heavy "prompt tips" content — mostly folk wisdom repackaged, not grounded in any controlled research.

### What the research actually shows about which elements improve output

This is where the honest answer is more nuanced than most prompting guides admit:

- **Role/persona assignment** has research-backed but modest and context-dependent effects. A 2023 paper from researchers at Google and various universities ("Better Zero-Shot Reasoning with Role-Play Prompting," Zheng et al.) found role prompting improved zero-shot performance on reasoning benchmarks, but the effect size varied widely by task. Importantly, some roles degraded performance — "You are an expert" is not always better than a neutral prompt. For a teen audience: role assignment is worth teaching as a good-practice habit with genuine benefits, but the module should not overstate it as "magic" (consistent with the module's own "this is not magic words" framing).

- **Few-shot examples** (showing the model examples of what you want) have some of the most consistent evidence behind them. Even one well-chosen example measurably narrows the output distribution toward the format and style you want. This is the technique most supported by controlled studies across task types. The Curriculum's "Show, don't just tell. Give an example of what you want. Even one example transforms output." is accurate and well-grounded.

- **Chain-of-thought / "think step by step"** — strong evidence for math and multi-step reasoning tasks. Less evidence for simple tasks where it can actually add noise or encourage overconfidence. For a teen audience the teaching is right: useful for logic and math, not a universal magic phrase.

- **Format instructions** — consistently useful, especially for structured output (lists, numbered steps, word limits). No controversial research findings. Keep as taught.

- **Iterate / treat first output as a draft** — not so much a prompt element as a mindset. All credible practitioner sources (Mollick, Anthropic, OpenAI guides) emphasize this. The Curriculum correctly positions it as the fifth piece — more of a habit than a syntax item.

### Recommendation for the module

Keep Role + Context + Task + Format + Iterate as the five-piece recipe exactly as drafted. It is:
- Consistent with what Anthropic and OpenAI actually teach in their own materials
- Simpler and more teen-accessible than CO-STAR or RISEN
- Accurate to the underlying research (with the caveats about role prompting not being magic, which the module already correctly flags)
- Already the canonical framing in AGENTS.md — changing it would break consistency with other modules

One small addition worth flagging for the module writer: the research distinguishes **instruction-following** (format, task specificity) from **context-giving** (role, background) — and the evidence is strongest for instruction-following. If the module ever needs to prioritize which element matters most on a quick rewrite, tell learners: **task specificity and format instructions are the highest-leverage changes; role is useful but not always critical.** This nuance probably belongs in Go Deeper rather than the core Concept block.

**The one folk-wisdom item to watch:** the common advice "longer prompts are always better" is not supported. Anthropic's own note ("A long prompt is not necessarily a good prompt," from the operating brief in the Source Material Library) is accurate. The module's emphasis on *clarity* over *length* is the right frame.

---

## 2. Best analogy / demo — is there a better one than "briefing a brilliant intern"?

**Verdict: the intern analogy is still the best all-purpose analogy, and must be kept as canonical (it's locked in AGENTS.md). Two supporting analogies are worth having ready; the climate-change before/after is good but can be improved for a teen audience.**

### The intern analogy — why it's still best

- Accurately captures: (a) high capability, (b) lack of situational context, (c) the need to brief well, and (d) why output quality depends on the briefer.
- Carries across multiple modules (Module 1 through Module 5 and beyond) without contradiction.
- Ethan Mollick's "On-boarding your AI Intern" is the most-cited single piece of writing on this analogy in 2024–2025 and is widely referenced by educators.
- The analogy also handles the "why a vague prompt gets a mediocre answer" problem intuitively: if you walked up to an intern and said "do climate change," they'd stare at you too.

**One useful caveat to know (not necessarily for the module):** Mollick himself notes the analogy has limits at the high end — a sufficiently capable model can outperform the person briefing it on certain tasks, which doesn't map to a typical intern. This is a good "Go Deeper" nuance if an advanced learner pushes back, not a reason to change the primary analogy for this audience.

### The climate-change before/after — assessment

The Curriculum's existing before/after example works, but it may not land as viscerally teen-relevant as it could:

- *Weak:* "explain climate change."
- *Strong:* "You're a science teacher explaining to a curious 9th grader. Explain why climate change happens using one everyday analogy, in under 120 words, then check my understanding with two questions."

This is a solid example. The problem is that "climate change" is a subject teens may have mixed feelings about (could feel like homework, could feel politically charged). The format upgrade is clear; the topic itself is not maximally motivating.

### Recommended before/after pairs — 2–3 for the module writer to choose from

**Option A — Essay help (most universally relatable)**
- Weak: "help me with my essay"
- Strong: "You are a writing tutor working with a 10th grader. My essay is about whether school start times should change. I have a thesis but my second paragraph is weak — I'm not sure if I've argued it or just stated it. Read this paragraph [pasted below] and tell me: what argument am I making, what evidence I'm missing, and one specific way to strengthen it. Keep your response under 150 words."
- Why this lands: every teen has been here. The difference between "help me with my essay" and the strong version is immediate and visceral — the weak prompt is useless, the strong one gives them something actionable.

**Option B — Study guide / quiz prep (school-relevant, reusable)**
- Weak: "make me a study guide for history"
- Strong: "You are a patient tutor. I'm studying for a quiz on the causes of World War I — specifically the MAIN acronym (Militarism, Alliances, Imperialism, Nationalism). I understand Nationalism but I'm shaky on Alliances and Imperialism. Give me a two-paragraph summary of each, using one real historical example each. Then give me three practice questions to test myself, starting easy and getting harder. No bullet points — write it out like you're talking to me."
- Why this lands: covers the whole recipe (role, context including what's weak, task, format with specific constraint), and the output is something they'll actually save and use.

**Option C — Creative project / social-relevant (motivating, slightly lighter)**
- Weak: "write a bio for my Instagram"
- Strong: "You're helping me write a short bio for my Instagram page. I'm a 15-year-old who does track, plays guitar, and posts a lot about sneaker culture. My vibe is casual but a little funny — not trying to sound fake-professional. Write three different versions: one short (under 30 words), one medium (30–50 words), one that uses an emoji or two. Don't use the words 'passionate about' or 'lover of.'"
- Why this lands: immediately personal, demonstrates format + constraint + negative instruction ("don't use these clichés"), and gives something they'll actually use today. The three-version request also introduces iteration in a natural way.

**Recommendation:** use **Option A (essay help)** as the primary module example — it maps most directly to something teens at 13–16 are doing weekly. Use **Option B** as the Guided Lab scenario (see section 3). Keep Option C in the writer's pocket as an alternative for learners who disengage from school examples. Do not use all three in the Core — pick one primary per the AGENTS.md "don't pad" rule.

**Also consider keeping the climate-change example** but moving it to a visual callout box as the "quick comparison" (it's compact and clear), while using Option A as the longer walkthrough the module builds piece-by-piece. This gives the module two before/afters without feeling padded: one fast visual comparison, one slow build-it-together walkthrough.

---

## 3. Teen-relevant examples for the Guided Lab

**Verdict: the Guided Lab should produce a reusable study-aid prompt the learner will use this week. Recommended scenario: "Build a personalized study guide prompt for a subject you're actually studying right now."**

### What school tasks teens actually use AI for (2024–2025)

Multiple survey reports and educator sources from 2024–2025 (Pew Research Center, Common Sense Media, Stanford HAI student surveys) converge on the same top use cases:

1. **Essay drafting, rewriting, and feedback** — by far the most common use
2. **Summarizing readings / class notes** — especially for long assigned texts
3. **Explaining concepts they didn't understand in class**
4. **Study guide / quiz prep generation**
5. **Brainstorming ideas** for projects, presentations, papers
6. **Writing emails / messages** (to teachers, for clubs)

All six are legitimate use cases where a well-crafted prompt makes a dramatic difference in output quality. The top three are where teens have the most frustrating experiences with AI (vague prompts → generic output → "AI is useless for this"), which makes them ideal for a before/after transformation.

### Three candidate Guided Lab scenarios

**Lab Candidate A — "Your reusable study guide prompt" (RECOMMENDED)**

Scenario: the learner builds a prompt for a specific subject they're studying *right now*. They fill in real details: subject, what they're covering, what they already understand vs. what's confusing, how they learn best (examples vs. diagrams vs. practice questions), and what format they want.

- **Step 1 — Role:** pick a tutor persona appropriate to the subject ("You are a patient AP Biology tutor" / "You are a history teacher who makes things interesting")
- **Step 2 — Context:** write 2–3 sentences: what subject, what topic, what they already know, what's confusing
- **Step 3 — Task:** exactly what they want ("explain X," "create a quiz on Y," "summarize Z in plain English")
- **Step 4 — Format:** specific constraints ("under 200 words," "use real examples, not abstract ones," "give me 5 practice questions, starting easy")
- **Step 5 — Iterate:** run it, look at the output, add one more constraint or clarification and re-run

- **Artifact:** a saved prompt they can reuse with real substitution slots (e.g., replace [TOPIC] each week)

Why this is the best pick:
- Uses a real, current need (whatever they're studying *this week*)
- The artifact is immediately useful and personally relevant (not a throwaway exercise)
- Maps cleanly onto the five-piece recipe, one element at a time — natural structure for the lab
- Learners who go back and reuse the prompt in a future week see the recipe's value long after the module

**Lab Candidate B — "Write a prompt for your next essay"**

Scenario: the learner picks a writing assignment they have coming up (or a common type: five-paragraph essay, persuasive piece, analysis) and builds a prompt for getting useful feedback rather than having AI write it for them.

- Emphasis on feedback prompts rather than drafting prompts — which sidesteps the AI-doing-your-homework issue and teaches a more sophisticated use case
- Slightly harder to scaffold well (learner needs to have an assignment in mind and a draft or thesis)
- Good for older teens (15–16) or writing-focused cohorts

**Lab Candidate C — "Build a prompt template for a reusable job"**

Scenario: pick something you do repeatedly (summarize YouTube videos, explain confusing news articles, write a weekly to-do breakdown) and build a reusable prompt for it.

- More open-ended, good for independent learners
- Harder to give clear success criteria (too varied)
- Better as an extension / Mission block than a structured Guided Lab

### Recommendation

Use **Lab Candidate A** as the primary Guided Lab. The essay-feedback variant (Candidate B) can be offered as a fork for the 15–16 cohort or learners who already do regular writing assignments.

**Concrete Guided Lab design sketch:**

```
Guided Lab: Build Your Study Prompt

You're going to build one strong prompt for a subject you're actually studying right now. 
By the end, you'll have something you can reuse every week.

Step 1 — Pick your subject and topic.
What are you studying right now? Pick one specific topic (not "science" — something like "cell division" or "the French Revolution" or "slope-intercept form").

Step 2 — Add a Role.
Fill in: "You are a [tutor/teacher] who [describes how you want them to teach]."
Example: "You are a patient math tutor who always explains with a real-world example first."

Step 3 — Add Context.
2–3 sentences: What's the topic? What do you already know? What's still confusing?
Example: "I'm studying slope-intercept form in Algebra. I understand what slope means but I keep mixing up where the y-intercept shows up in the equation."

Step 4 — Add the Task.
Exactly what you want back: an explanation, a quiz, a summary, a comparison.
Example: "Explain slope-intercept form step by step, using a graph example and a real-life example."

Step 5 — Add Format.
How long? What style? What should it NOT do?
Example: "Keep it under 150 words. No bullet points. End with two practice problems."

Step 6 — Run it. Read the output. Add one more thing.
What did you get that you didn't want? What was missing?
Add one more instruction and re-run. This is Iterate.

Save your finished prompt. You can reuse it next week — just change the topic.
```

**Success criteria:** the learner has a saved prompt (5 elements filled in) that they ran at least once and iterated on once. Output should be meaningfully better than what "explain [topic]" would produce. The artifact is the saved prompt, not just the AI's answer.

**Potential failure modes to watch for:**
- Learner fills in minimal/vague context ("I'm confused about math") → output stays generic → they don't see the transformation. Fix: prompt them with "be specific enough that a tutor who knows nothing about your class could help you."
- Learner rewrites and gets a worse output (this happens) → frustrating and undermines the lesson. Fix: tell them iteration sometimes means trying a different angle, and that the first rewrite doesn't always win — that's normal.
- Learner spends all their time on Step 1 (picking a subject) → gets bogged down before the recipe kicks in. Fix: have a default scenario ready ("if you're not sure what to pick, use this: [example]").

---

## 4. Real business example — prompting making a dramatic difference professionally

**Best pick: legal brief prompting, with a concrete contrast story. Second pick: GitHub Copilot's "context-loading" pattern at scale.**

### Primary recommendation — the legal prompting contrast

By 2024–2025, the legal sector was the most well-documented industry for prompt-quality making a concrete, measurable difference. The hallucinated-citations problem (from Module 1 research notes: 200+ court cases involving AI-fabricated citations by 2025) created a sharp contrast:

**The bad prompt pattern:** lawyers asking AI to "find cases that support my argument" with no constraints — resulting in convincingly-cited but fabricated cases (Mata v. Avianca, 2023; the Morgan & Morgan case, 2025; dozens of others). These lawyers lost money, faced sanctions, and in some cases were fined or disciplined.

**The good prompt pattern:** law firms that developed internal "AI prompting protocols" by 2024–2025 added specific constraints: "Use only the cases I paste below as source material. Do not generate any case names, citations, or holdings from your training data. If no supplied case supports the argument, say so explicitly." This is the "grounded" approach — and it's a direct parallel to the Module 5 recipe (context: here's the source material; constraint: don't invent; task: analyze only from what I gave you).

**Teen-accessible framing:**
> "Some lawyers started using AI to write legal briefs — and a few got in serious trouble because the AI confidently invented case citations that didn't exist. The lawyers who had trained themselves to write tight, constrained prompts avoided the problem. Same AI, different prompting habits. The ones who lost got fined and embarrassed in court. The ones who prompted well — including saying 'only use what I give you, don't make things up' — got faster, accurate briefs. That's a real job where prompt quality made a career difference."

This example works because:
- It has clear, documented stakes (court fines, professional discipline — real consequences)
- It's a familiar adult profession teenagers can picture
- It directly maps to Module 5's techniques: context-giving, constraint-setting, the "say what you don't want" technique
- It also foreshadows Module 6 (grounding) naturally

Sources: the Morgan & Morgan case (Feb 2025, three lawyers sanctioned for AI-fabricated citations) is well-documented across legal press (Reuters, ABA Journal). The California attorney fined $10,000 (CalMatters) is also documented. These are referenced in the Module 1 research notes.

### Second option — GitHub / developer prompting at scale

By 2025, large software companies (Microsoft, GitHub, Google) had published internal studies on developer productivity with AI coding assistants. The consistent finding: developers who wrote specific, contextual prompts ("I am refactoring a function that does X, it currently uses Y pattern, I need it to handle Z edge case without breaking W") got code they could use directly. Developers who wrote "fix my code" or "make this faster" with no context got generic or wrong answers.

GitHub's published research (GitHub Copilot research reports, 2024) showed experienced developers used it very differently from beginners — the experienced ones treated it like a junior colleague who needed a clear brief, not a magic oracle.

**Teen-accessible framing:**
> "GitHub, the platform where most of the world's software is built, found that developers who treated AI like a 'junior teammate who needs a good brief' got dramatically better code. Developers who wrote vague requests — 'fix this,' 'make it faster' — got answers that sounded plausible but were often wrong. The better developers wrote prompts that looked almost exactly like our five-piece recipe: here's what I'm building, here's the context, here's exactly what I need, here's the format. Same tool, wildly different results."

This example works well for teens who are interested in coding or building (sets up Module 9 naturally).

**Module writer's choice:** the legal example is probably more vivid and dramatic for a general teen audience (stakes, consequences, a clear "loser" and "winner" story). The GitHub example is better for the tech/building-oriented cohort. Consider leading with legal and mentioning GitHub as a one-liner ("same thing is true in software development, where GitHub found...").

---

## 5. The operating brief fold-in — what belongs in Module 5 vs. Module 10?

**Verdict: introduce the operating brief at the end of Module 5 as the "level-up" — but teach only Goal, Context, Task/Deliverables, and Constraints. Leave Inputs and Verification for Module 10 (Agents) where they're more meaningful.**

### The operating brief's six parts and where each belongs

The full brief from the Source Material Library:

| Part | Best module | Rationale |
|---|---|---|
| **Goal** | Module 5 | Direct parallel to "Task" in the five-piece recipe. Easy uplevel: "instead of 'what you want,' write a clearer statement of what success looks like." |
| **Context** | Module 5 | Already in the recipe. At Module 5 level, just reinforce good context-giving. |
| **Inputs** | Module 10 (Agents) | "What files, tools, APIs, or data should it use" only makes sense once you're giving an agent access to tools. Not meaningful in a simple chat prompt. |
| **Constraints** | Module 5 (partially) | Ties directly to "say what you don't want" technique already in the Curriculum. Simple version: "what should it avoid or preserve?" Full version with scope/permissions belongs in Module 10. |
| **Deliverables** | Module 5 | Maps naturally to "Format" in the recipe. Uplevel: "instead of just 'format,' specify the exact artifact you want back." |
| **Verification** | Module 10 (Agents) | "What evidence will prove the work is correct" is meaningless in a single chat interaction. It makes perfect sense for a multi-step agent task where you need to know when it's done. Teach here and it'll confuse — teach in Module 10 and it clicks immediately. |

### What Module 5 should teach

Introduce the operating brief as the "grown-up version" near the end of the module — after the Guided Lab, not before. Sequence:
1. Core: five-piece recipe (Role + Context + Task + Format + Iterate)
2. Techniques: examples, step-by-step, say what you don't want, break big asks
3. Guided Lab: build a study prompt using the recipe
4. Level-up callout: "when the task gets bigger, here's the grown-up version"

Show only the four most relevant parts for a chat context:
```
Goal:         What are we trying to accomplish? (one sentence)
Context:      What should it understand about my situation?
Deliverables: What exactly should it give me back?
Constraints:  What should it avoid, not change, or ask me about first?
```

Frame it as: "Same idea as the five-piece recipe, more precise language. You'll use this exact format in Module 10 when we give AI agents real tasks to run."

**Do not teach Inputs and Verification in Module 5.** They'll make sense in Module 10 in the context of an agent that needs files/tools and has a clear stopping condition. Teaching them here risks making the brief feel abstract and heavy.

### Where to position the operating brief in Module 5

The Master Build Plan says "teach the simple version in 5, full in 10" — this is the right call. The module should:
- Put the operating brief **after** the Guided Lab (not before) — introduce it as a "now that you've built one prompt the five-piece way, here's how the pros formalize it"
- Make it a light "level-up" section, not a separate lab — no additional exercise, just show the template and say "you'll use this for real in Module 10"
- Use one of the Guided Lab outputs as an example of what it looks like cast into the operating brief format — this is a satisfying "look, you were already doing this" moment

---

## 6. Try-It design — what makes the before/after work, and what are the failure modes?

**Verdict: the weak→strong Try-It is well-supported by learning science. The key design principle is to make the transformation visceral within one screen-view. Main failure modes are fixable with two design choices.**

### Why before/after Try-Its work (the learning science)

The "two-condition comparison" format (run A, then run B with one key change, compare) works because of **concrete comparison**: humans are far better at evaluating relative quality than absolute quality. Seeing two outputs side-by-side removes the subjective difficulty of deciding "is this good?" and replaces it with "which of these is better and why?" — a much easier cognitive task.

This is analogous to the A/B testing mental model (familiar to anyone who's seen ads or done any market research) and also to the "before and after" structure used in design, writing feedback, and code review. All of these share the insight that contrast makes quality visible.

**For prompting specifically:** the research on "interleaved" instruction (teach concept, immediately apply, compare) consistently outperforms "block" instruction (teach concept, wait, apply later). The Try-It directly after the Concept section — rather than after a break — is the right design choice.

### What makes the transformation visceral and fast

Three design principles that matter most:

1. **The weak prompt must be genuinely weak, not medium.** "explain climate change" is weak enough. "Write a short essay about climate change" is medium — it'll produce something plausible and the learner won't see a dramatic enough difference. Make the weak prompt the kind of thing someone types in frustration: "help me study," "explain this," "write a bio." Short, vague, no recipe elements.

2. **The strong prompt must be built piece-by-piece, not presented as a finished block.** If the learner sees the strong prompt all at once and runs it, they'll feel like they're following a script without understanding it. Better: build the strong version in the module text (step by step, adding each element with an annotation), then run it. The module writer should build the strong prompt live on the page, not present it pre-assembled.

3. **The comparison must happen within one view.** If the learner has to scroll to compare weak output vs. strong output, the contrast fades. Ideal: show both outputs side-by-side in a visual callout box (or have the learner open two tabs, one per prompt). The contrast needs to be immediate and visible at the same time.

### Main failure modes

**Failure mode 1: learner picks a weak prompt that happens to get a decent answer anyway**
Some short/vague prompts get pretty good answers from capable 2025-era models (the models have gotten better at inferring intent). If a learner runs "explain photosynthesis" and gets a decent explanation, they'll feel the lesson is wrong. Fix: give them the weak prompt to use (don't let them choose their own for this exercise), or pick domains where the vague prompt is reliably poor: "help me with my essay" is still reliably useless without context. Open-ended creative or personal tasks still benefit dramatically from specificity.

**Failure mode 2: learner writes a "strong" prompt that is still vague, sees marginal improvement, concludes prompting doesn't matter**
The most common failure. Fix: give them a fill-in-the-blanks template for the strong version (the CBC beginner template from the Source Material Library is ideal here). They fill in actual content, not generic placeholders.

**Failure mode 3: learner gets confused about which element to change during the Iterate step**
They have a strong prompt, they want to improve the output, but they don't know what to change. Fix: give them a specific "what to look for" checklist: if the answer is too long → add a word limit; if it's too generic → add an example; if the tone is wrong → specify it; if it's missing a key point → add it to the Context. This turns Iterate from "redo it somehow" into a diagnostic process.

### Recommended Try-It design

1. Show the weak prompt: `"help me study for my quiz"` (don't explain it yet — just show it, run it in the sandbox, see what comes back)
2. Annotate the output: "Here's what you get. What's missing? It doesn't know: what subject, what level, what kind of help, how long you have..."
3. Build the strong prompt on the page, one element at a time:
   - Add Role → re-run → see change
   - Add Context → re-run → see change
   - Add Task → re-run → see change
   - Add Format → final run
4. Compare weak output vs. strong output side-by-side
5. Learner tries their own: take one weak prompt they'd normally type, apply the recipe, compare

This is slightly more structured than the Curriculum's current "take one weak prompt, rewrite it, run both" — the Curriculum version is too open-ended for a first Try-It. The guided version (annotated step-by-step build) works better as the initial exercise, with the open-ended "now do your own" as the follow-on.

---

## 7. Go Deeper references

Notes on each: I could not verify live link status for any of these (browser/fetch tools unavailable). All are well-established resources that were active as of my training cutoff (Aug 2025). The module writer should do a quick link check before publishing. No SEO content-farm recommendations included.

**Highly recommended (non-vendor, credible, beginner-accessible):**

1. **Anthropic — "Prompt Engineering Overview"**
   - URL: https://docs.anthropic.com/en/docs/build-with-claude/prompt-engineering/overview
   - What it is: Anthropic's own plain-English guide to effective prompting. Not too technical, not too marketing-y. Covers: clarity, examples, format specification, chain-of-thought, role assignment. Well-organized. Updated regularly.
   - Why it works for a teen: short sections, readable, practical. The "be clear and direct" framing will feel familiar from the module.
   - Caveat: Claude-specific examples, though the principles are universal.
   - Verification: live as of Aug 2025; recommend a quick check before publishing.

2. **OpenAI — "Prompt Engineering Guide"**
   - URL: https://platform.openai.com/docs/guides/prompt-engineering
   - What it is: OpenAI's own developer-facing but readable guide. Six strategies, each with concrete examples. Covers: clear instructions, examples, step-by-step reasoning, format specification.
   - Why it works: pairs well with Anthropic's guide to show that the recipe isn't vendor-specific (both major platforms recommend the same core elements). Good "see, it's not just one company saying this" reference.
   - Caveat: written for developers but mostly accessible to a sharp teen.
   - Verification: live as of Aug 2025.

3. **Ethan Mollick — "A guide to prompting AI (for what it's worth)" (One Useful Thing)**
   - URL: https://www.oneusefulthing.org/p/a-guide-to-prompting-ai-for-what (approximate URL — verify)
   - What it is: a practitioner/educator's plain-English take on prompting. Mollick (Wharton professor, widely followed AI educator) writes accessibly and honestly about what works, what doesn't, and why. Repeatedly updated as the landscape changes.
   - Why it works for a teen: Mollick writes in a conversational, non-hyped voice that will feel familiar after the module. He names the limits clearly.
   - Note: Mollick's Substack (oneusefulthing.org) has multiple good prompting posts — verify which specific post/URL to cite. His 2023/2024 "working with AI" posts are consistently among the most-linked non-vendor AI resources.
   - Verification: Site is active as of Aug 2025; specific post URL needs manual verification.

4. **CSET — "The Surprising Power of Next-Word Prediction: Large Language Models Explained"**
   - URL: https://cset.georgetown.edu/article/the-surprising-power-of-next-word-prediction-large-language-models-explained-part-1/
   - What it is: Georgetown CSET's accessible explainer. Already referenced in Module 1 research notes. For Module 5, the Go Deeper angle is the section where they explain that LLMs respond strongly to framing — which is the underlying reason prompting matters.
   - Why it works: gives the "why prompting works" explanation grounded in how LLMs actually process text, without being a technical paper.
   - Verification: verified live in Module 1 research pass. Recommend re-checking.

5. **Learn Prompting — learningprompting.org**
   - URL: https://learnprompting.org
   - What it is: an open-source, community-maintained guide to prompt engineering. Started in 2022, maintained through 2025. Broader and more comprehensive than the vendor guides — covers techniques like chain-of-thought, few-shot, zero-shot, role prompting, and more advanced topics in accessible language.
   - Why it works for a teen: free, well-organized, readable, not a vendor product. A curious teen who wants more can go much deeper here without hitting a paywall.
   - Caveat: quality varies by section (community-written); recommend pointing to the "Basics" section specifically rather than the whole site, to avoid overwhelming a beginner.
   - Verification: site was active as of Aug 2025; URL needs a quick check before publishing.

**Not recommended:**
- Generic "top 10 prompting tips" content (Medium posts, LinkedIn carousels) — folk wisdom, not grounded.
- Most YouTube "prompt engineering" videos — fast-moving, usually tool-specific, lack rigor.
- Prompt marketplaces (PromptBase, etc.) — selling prompts as magic, not teaching principles.

---

## 8. Open questions / judgment calls for the module owner

These are decisions research can inform but not make. The module writer needs to sign off on these before drafting.

**Q1: Should the five-piece recipe be taught as a strict formula or as flexible principles?**

The Curriculum currently presents it as a recipe (numbered, five items). This is pedagogically correct for first exposure — learners need something concrete and repeatable to hold onto. The risk is that it feels mechanical ("I must hit all five boxes") rather than intuitive ("I'm giving someone a good brief").

Recommendation: teach it as a formula first (for the Try-It and Guided Lab, where the scaffolding helps), then add one sentence at the end: "Once you've used the recipe a few times, you'll stop thinking of it as a checklist and just start writing clear prompts naturally — the recipe becomes instinct." This manages the risk that learners feel they're failing if they don't hit all five items in every prompt.

**Q2: How much to lean on the intern analogy vs. other framings?**

The intern analogy is canonical (AGENTS.md says so) and should be the primary frame. The only question is whether to add a second, supporting analogy for learners who don't connect with the intern image (e.g., some teens haven't had work experience and may not relate to "briefing a new hire").

A supporting analogy worth having: **briefing a very smart stranger who just moved to your city.** They're brilliant, they've read about your city extensively, but they don't know your neighborhood, your school, your situation. If you ask them "where should I eat?" you'll get generic answers. If you say "I'm near the train station, I have $15, I want something fast and non-spicy, not a chain" — they'll nail it. This maps the same brief-the-brilliant-but-uninformed-person structure without requiring the intern frame. Possibly better for younger end of the 13–16 range.

**Q3: Where exactly does the operating brief get introduced — before or after the Guided Lab?**

Strong recommendation: **after the Guided Lab.** Sequence matters here:

- Before: learners first encounter the operating brief (six parts, feels heavy), feel overwhelmed, then do the Lab already feeling like they're missing something. The Lab output also won't use the brief's language, creating confusion.
- After: learners complete the Guided Lab using the five-piece recipe, have a concrete output in hand, then see the operating brief framed as "here's the same idea, formalized." They'll recognize their Lab prompt in the brief's structure — a satisfying "oh, I was already doing that" moment.

**Q4: Should the module use the CBC beginner prompt template as the actual fill-in scaffold for the Lab, rather than building the recipe from scratch?**

The CBC template from the Source Material Library:
```
Create [output] for [audience].
The purpose is [goal].
Use the attached [source material] as the source of truth.
It should feel [three useful adjectives].
Include [requirements or constraints].
Show me a first version for review before publishing, sending, sharing, or changing access.
```

This template is close but not quite right for the Guided Lab as designed — it's built around a "create output for audience" structure (very suited for marketing/content creation) but not the "help me learn / study aid" use case. For the study-guide Lab scenario, a custom fill-in works better (see Section 3). However, the CBC template could appear as a sidebar example of what the recipe looks like "in the wild" — useful framing that connects back to the Source Material note.

**Q5: What to do about "prompt injection" — should it be mentioned in Module 5?**

Module 12 (Safety) covers prompt injection. The question is whether Module 5 should plant a seed. Brief mention: "Because prompting is powerful, people sometimes hide instructions inside content they share with you (a webpage, a document) — trying to trick the AI into doing something you didn't intend. We'll cover this in Module 12."

Recommendation: one sentence maximum, not a full treatment. The emotional target of Module 5 is "the power is in how I ask" — lingering on prompt injection risks undercutting that confidence. Plant the seed, defer the treatment.

**Q6: Should Iterate be positioned as the fifth "element" of a prompt, or as a separate mindset?**

There's a real argument that Role + Context + Task + Format are the four *elements*, and Iterate is a *habit* (what you do after the first run) — not an element of the initial prompt. Treating it as a fifth prompt element is slightly misleading (you don't write "Iterate: [something]" in your prompt).

However, it's worth keeping in the five-piece list for a simple reason: it sets the expectation upfront that one run is not always enough. If you drop it from the list, learners think the recipe is "write one prompt, get a perfect answer." Keeping it as the fifth item — even though it's really a mindset, not a prompt component — is the pedagogically correct choice for this audience.

If the writer wants to be precise, a small callout could note: "The first four pieces go into your prompt. Iterate is what you do after you read the output."

---

## Couldn't verify

- All Go Deeper URLs: browser access was unavailable for this session. Specific URLs in Section 7 are provided based on training knowledge but have not been live-checked. The module writer must verify each before publishing. The Anthropic and OpenAI docs URLs are the most likely to have changed (docs get reorganized frequently); the oneusefulthing.org and CSET URLs are more stable.
- The specific Ethan Mollick post URL for "A guide to prompting AI" — the URL above is approximate. Verify against oneusefulthing.org directly.
- Specific statistical claims about teen AI use (Pew, Common Sense Media, Stanford HAI surveys referenced in Section 3) — I did not verify the specific survey numbers or exact publication dates. The pattern (essay help, summarizing, explaining concepts are the top use cases) is corroborated across multiple independent reports I'm aware of through training, but the module writer should not cite a specific statistic without pulling the actual survey source.
- CO-STAR framework origin: attributed to Singapore GovTech via multiple blog posts. The module writer should verify this attribution if CO-STAR is mentioned at all (it's mentioned only in the "not recommended" discussion in Section 1 — probably safe to leave the origin uncited there).

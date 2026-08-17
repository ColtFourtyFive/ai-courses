# Research Notes — Module 4: Picking the Right Model

> Research pass for the module writer. Not the module itself — findings, recommendations, and judgment-call flags. Written Aug 2026. Web search was not available for this pass; findings draw on (a) prior module-02.md research (verified Aug 2026 landscape), (b) files read in this session, and (c) trained knowledge through Aug 2025. Anything flagged "verify live" should get a 60-second manual check before publishing.

---

## 1. Concept check — the selection criteria

**The Curriculum's list (task type/difficulty, speed, cost, privacy, extras like long context and reasoning) is still the right starting framework for 2026. It holds up. Minor gaps and adjustments below.**

### The five criteria — verdict on each

**Task type and difficulty — keep, and promote to the top.** This is the most durable and most important criterion. The key principle: not all tasks reward a heavier model. A "heavy" model (Opus-tier, GPT-5 top tier, Gemini 3 Pro) gives you more careful reasoning, more nuance, longer coherent outputs — but at the cost of speed and, in paid contexts, money. A "fast/light" model (Haiku-tier, Flash-tier) is snappier and cheaper, and perfectly adequate for summarizing, reformatting, simple Q&A. The right question to ask first is always: "How much thinking does this actually need?" Most teen use cases (homework explanation, summarizing notes, rewriting a draft) don't need the heavy tier. A few do (analyzing a complex argument, writing a multi-part research plan, anything involving careful multi-step reasoning).

**Speed — keep, but reframe for teens.** "Speed" to a professional means tokens/second at scale or API latency. To a teen it just means: "does it make me wait?" Light/fast tiers feel nearly instant. Heavy tiers sometimes show a visible "thinking" delay (especially explicit reasoning models — see below). For synchronous use (real-time back-and-forth in a chat), speed matters. For background tasks where you walk away, it doesn't. Recommend framing as: "If you're waiting at your keyboard, pick fast. If you're walking away and coming back, speed doesn't matter."

**Cost — keep for free-vs-paid framing, not for pricing specifics.** For most teens, "cost" means: does this require a paid subscription or not? Lighter models (Haiku-tier, Flash, GPT mini variants) are often accessible on free tiers or included in lower-cost plans; heavier models require paid tiers (Claude Pro/Max, ChatGPT Plus, etc.). Specific pricing ages within months — don't print a dollar amount. The durable principle: "heavier model = more likely to be behind a paywall or to eat your daily quota faster." This is a real teen concern — running out of free-tier messages mid-homework-session is a concrete, felt problem.

**Privacy — keep, but be specific about what it means for teens.** The Curriculum lists privacy as a criterion, and it is, but teens need it unpacked differently than professionals do:
- The relevant teen question isn't "is this GDPR-compliant?" It's: "Am I pasting anything I wouldn't want my school, my parents, or a stranger to see?" and "Is this being saved and used to train future models?"
- Most consumer AI tools (Claude.ai, ChatGPT, Gemini) offer some control here (opt-out of training data, history off modes) but the defaults vary and change. The more privacy-relevant criterion for teens is: *don't paste your real full name, your address, another person's personal info, or your school ID into any AI tool* — regardless of which model you're using.
- Privacy as a *model-selection* criterion (vs. a general usage habit) matters most when a teen is choosing between a local/offline model (nothing leaves the device) vs. a cloud-based one. This is a niche use case in 2026 for most teens, but worth one sentence: "If the task involves genuinely private info, look for a local model or don't paste the private part in at all."
- **Verdict: keep privacy as a criterion, but the module's job is to make it concrete and teen-legible, not keep it abstract.**

**Extras (long context, reasoning) — keep, but split into two because they're different things.**

- *Long context*: relevant when the teen is pasting a large document, a whole book chapter, many files at once. The practical felt difference: with a short context model you hit a "can't fit more" error or the model starts ignoring what you pasted earlier. With a long context model you can dump in the whole thing. For most everyday teen tasks (a homework prompt, a few paragraphs to summarize), long context is irrelevant. It matters for research projects with many sources, or analyzing a whole book.
- *Reasoning mode*: this is a genuinely new and important addition to the 2026 landscape that the Curriculum doesn't fully foreground. All major providers now offer an explicit "reasoning" or "thinking" mode (Claude's extended thinking, OpenAI's "o"-series descendants, Gemini's thinking mode). These feel different: they're slower (visible "thinking" before answering), they tend to be more thorough on multi-step problems, and they're notably better at catching their own errors before outputting. For a teen: use reasoning mode for math, logic puzzles, careful essay arguments, or anything where you've already gotten a bad answer and want the model to actually think harder. Skip it for quick questions, summaries, creative writing (where the overhead isn't worth it).

### Criteria the Curriculum misses that a teen would care about

**Modality support** — "Can it handle images/audio/video, or text only?" This isn't in the Curriculum's Module 4 list but is increasingly a real selection criterion in 2026. A teen picking a model for a science lab where they want to photograph a diagram and ask questions about it needs a multimodal model. This criterion is less about model tiers and more about capability: "does this tool support what I'm handing it?" Worth one line in the module: "If your task isn't text-only, check that the model can handle what you're giving it."

**Tool/integration availability** — Which model is inside the tool that already does the other things you need? This is a practical criterion teens face: "I want to use something that can also search the web / read my Google Docs / run code." The model matters less here than which app/harness wraps it — this ties back directly to Module 2 ("the harness, not the brain"). Worth a brief call-out: "Sometimes 'which model' is answered by 'which app has the tools I need' — and that's fine."

**What's actually available to you right now** — the unglamorous but real first criterion. A teen may only have access to what their school provides, what their parents' account includes, or what's free-tier. The practical framework should acknowledge: "Start with what you have. The selection criteria matter *among the options you can actually use*." This prevents the module from feeling like it's for someone with unlimited money and ten accounts.

### Criteria less relevant for teens vs. professionals

**Throughput / rate limits at scale** — professionals care about how many API calls per minute. Irrelevant for a teen using a chat interface.

**Fine-tuning / custom model training** — out of scope for Module 4 (belongs in the optional Builder track, Module 11).

**Latency SLAs and uptime guarantees** — enterprise concerns; not a teen selection factor.

**Recommendation for the module writer:** Keep all five Curriculum criteria; add a one-liner on modality support and a realistic "start with what you have" framing. Split "extras" into two separate mini-criteria (long context vs. reasoning mode) since they serve different tasks and are now distinct enough that teens encounter them as separate toggles in real products.

---

## 2. The model landscape — what a teen needs to know in 2026

**Do not duplicate Module 2's work.** Module 2 research notes (module-02.md) already confirm: Claude family = Opus / Sonnet / Haiku tiers; OpenAI = GPT-5.x family; Google = Gemini 3 family with Pro and Flash variants. Module 4 needs to go one level deeper — *what would a teen actually feel and notice* between tiers, not what the benchmark leaderboard says.

### The tier principle (principle-based, not a ranked list)

There are roughly three functional tiers across all the major providers, and the pattern is consistent enough to teach as a principle:

**Heavy tier** (Opus, GPT-5 top tier, Gemini 3 Pro):
- Noticeably more careful and thorough on complex tasks
- Slower (sometimes a visible delay, especially in reasoning mode)
- More likely to be paywalled or to hit free-tier limits faster
- When to use: complex analysis, multi-step reasoning, writing something where quality matters enough to wait for it, anything you've already tried on a lighter model and found wanting

**Middle tier** (Sonnet, standard GPT-5, Gemini 3 standard):
- The "daily driver" — solid quality, reasonable speed
- The sweet spot for most real tasks: essay drafts, explaining concepts, brainstorming
- When to use: most of the time

**Fast/light tier** (Haiku, Flash, GPT-mini variants):
- Very fast (nearly instant responses)
- Lower quality on nuanced tasks — fine for simple things, often noticeably worse on complex ones
- More likely to be free or cheap
- When to use: simple lookups, quick reformatting, tasks where "good enough fast" beats "great but I'm waiting"

**Reasoning models** (now offered by all major providers as a mode or a separate model variant — Claude extended thinking, OpenAI o-series descendants, Gemini thinking mode):
- Noticeably different *feel*: visible "thinking" before answering, often longer output
- Better at math, multi-step logic, catching contradictions
- Slower and sometimes more expensive
- Not always better for open-ended creative tasks — the overhead can actually produce more rigid output
- When to use: math problems, logic puzzles, carefully structured arguments, debugging a plan that keeps going wrong

### The "felt differences" a teen would actually notice

| Situation | What they'd notice |
|---|---|
| Used fast tier for a complex essay | Output is shallow, generic, misses nuance — feels like the model phoned it in |
| Used heavy tier for a quick vocab definition | Had to wait 10–15 seconds for a one-sentence answer that a fast model would have nailed in 2 seconds |
| Used standard model for a multi-step math proof | Got a confident but wrong answer partway through — the model stopped checking its own work |
| Used reasoning model for a quick "what's the capital of France?" | Got a correct answer but waited 5+ seconds for thinking that wasn't needed |
| Used a text-only model on a photo of a graph | Got an error or a flat "I can't see images" |
| Used a tool with web access vs. one without | Completely different answer on "what's happening this week in [topic]" |

### Principle to teach: "use the lightest model that gets the job done"

This is the durable takeaway from how professionals actually use multi-model setups. Heavy models exist because some tasks need them. But using a heavy model for everything is like driving a pickup truck to buy a sandwich — you can, but you're wasting something. The practical habit: start with the middle tier (or whatever you have), and only reach for the heavy tier or reasoning mode when you've hit a real quality ceiling.

### What to say about specific model names in the Core

Consistent with module-02.md's recommendation: use tier names (heavy / middle / fast) as the primary vocabulary; name Claude/GPT/Gemini as family examples, never a specific version number. Version numbers are stale within a quarter. The tier principle (and which tier your current tool falls into) is the durable thing to teach.

**One line that captures it:** "Every major AI provider has roughly three tiers: fast and cheap, solid and balanced, and heavy and thorough. Which tier you need depends entirely on the task."

---

## 3. The "test two options" Guided Lab

**The core design principle:** the lab should produce a *concrete, specific difference* the learner can see and articulate — not just "this one felt better." The task has to be rich enough that quality varies meaningfully between models (or tiers), but short enough to run twice in 10–15 minutes.

### Recommended task: "Build me a study plan for something I actually have coming up"

This is the strongest candidate because:
- Every teen has a real upcoming test, project, or deadline
- It involves planning (benefits from reasoning), synthesis (benefits from knowledge), and personalization (tests whether the model asks clarifying questions or just assumptions)
- It's concrete enough to evaluate: does the plan have useful steps? Does it make sense for the timeline? Does it ask what you already know?
- It's not a task where "longer = better" — a good study plan is tight and actionable, not padded

### Lab sketch

**Setup (2 min):** Learner picks a real upcoming task — a test, a project, an essay they have to write. They write one sentence describing it: "I have a [AP Bio test / history essay / math quiz] in [X days] and I want to [pass / do well / finish it without pulling an all-nighter]."

**The test prompt (same for both models):**
> "I have a [their task] in [X days]. My goal is [their goal]. Give me a concrete, day-by-day study plan that's actually doable. Be specific — not generic advice."

**Round 1 (5 min):** Run the prompt in Model A (their default or free-tier tool). Paste in the exact prompt, no extra explanation. Read the output. Fill in the scorecard (below).

**Round 2 (5 min):** Run the exact same prompt in Model B (a different tool, or the same tool's different tier/mode). Same prompt, no changes. Read the output. Fill in the scorecard.

**Compare (3 min):** Look at both outputs side by side. Answer: which one would you actually use, and why?

### The comparison criteria (scorecard for the lab)

These are the four things that matter for this specific task — chosen because they're observable and distinct, not just "felt better":

1. **Specificity** — Does it give concrete steps ("review Chapter 7 flashcards for 20 minutes") or vague advice ("review your notes")?
2. **Fit to your timeline** — Does it actually work in the time you have, or does it assume infinite time?
3. **Confidence calibration** — Does it claim to know things it can't know (how hard the test will be, what will be on it), or does it appropriately hedge and ask what you already know?
4. **Would you actually use it?** — Is this something you could start on right now, or is it too generic to act on?

**Scoring: 1–3 on each dimension. Max 12 per model.** A model with a score of 10–12 gave a genuinely useful output. 7–9 is decent but needs editing. Under 7 is generic/unusable.

### Scorecard template

```
Task I tested: _______________________
Days until deadline: ______

                       Model A          Model B
                    (name/tool):     (name/tool):
Specificity         __ / 3           __ / 3
Fit to timeline     __ / 3           __ / 3
Confidence cal.     __ / 3           __ / 3
Would I use it?     __ / 3           __ / 3

TOTAL               __ / 12          __ / 12

Winner: ____________

One thing the winner did better:
_______________________________________

One thing neither did well:
_______________________________________
```

**Success criteria for the lab:** learner can name *one specific thing* the better model did differently — not just "it felt better" but "it broke the plan into days instead of giving me a list of topics." That's the discernment skill the module is building.

### Design notes for the module writer

- Keep the task flexible — "something you actually have coming up" is better than a fixed hypothetical, because it makes the quality difference personal and immediately visible.
- The lab works whether the learner compares (a) two different providers, (b) two tiers of the same provider, or (c) the same model with and without reasoning mode. Don't prescribe one — let them use what they have access to. The principle is the same either way.
- If a learner only has access to one tool: they can still run the lab by comparing the same model with reasoning mode on vs. off, or by comparing two different personas/system prompts. It's not ideal, but it preserves the "test don't trust" habit.
- 10–15 min is achievable: 2 min setup, 5 min round 1, 5 min round 2, 3 min compare. Tight but doable if the task is pre-chosen.

---

## 4. The reusable scorecard — artifact design

**The artifact's job:** a teen should be able to pull this up before starting any AI-assisted task and have a clear answer in 2 minutes. It should not be a 20-row spreadsheet. It should not be "it depends" all the way down. It should produce a concrete recommendation.

### The four questions that actually matter

After stripping out everything a professional would add (latency SLAs, throughput, fine-tuning, API cost), the dimensions that drive a teen's model choice in 2026 reduce to four:

**1. How hard is this task, really?**
- Quick / simple (answer a question, reformat text, look something up) → fast/light model is fine
- Medium (draft an essay, summarize a long document, brainstorm seriously) → middle tier
- Complex / high-stakes (multi-step reasoning, careful argument, something where being wrong really matters) → heavy tier or reasoning mode

**2. Do I need it fast?**
- Yes, I'm waiting at my keyboard → skip reasoning mode; use the fastest good-enough model
- No, I'll walk away → use a heavier model if the task warrants it

**3. Is anything sensitive in what I'm pasting?**
- Yes (real full name + personal details, someone else's private info, school account credentials, medical/financial info) → stop; don't paste it in; either use a local model or remove the sensitive part
- No → proceed normally

**4. Does this task need a special capability?**
- Images/audio/video → confirm the model is multimodal
- Web search / current info → confirm web access is on
- Code execution → confirm code interpreter is available
- None of the above → standard text model is fine

### The scorecard template (reusable, 2-minute version)

```
MODEL SELECTION SCORECARD
Task: _________________________________

Q1 — How hard is this task?
 [ ] Quick/simple     → fast model OK
 [ ] Medium           → standard model
 [ ] Complex/stakes   → heavy or reasoning mode

Q2 — Do I need it right now?
 [ ] Yes, waiting     → skip reasoning mode
 [ ] No, walking away → reasoning mode OK if task warrants

Q3 — Anything sensitive I'm pasting?
 [ ] Yes              → STOP — remove the sensitive info first
 [ ] No               → proceed

Q4 — Special capability needed?
 [ ] Images/audio/video?        need multimodal
 [ ] Current/live info?         need web search ON
 [ ] Code to run?               need code interpreter
 [ ] None of above              standard text is fine

RECOMMENDATION:
_________________________________
(e.g., "Standard model, web search on, no reasoning mode needed")
```

### Design principles for the artifact

**It should produce a recommendation, not a list of factors.** The bottom line of the scorecard is a fill-in, not another checklist. The learner writes a one-line decision: "use Haiku/Flash/whatever fast model, no reasoning" or "use heavy tier with reasoning mode, web search on."

**It stays valid even as model names change.** Nothing in the scorecard references a specific model name or version number. The criteria (task complexity, speed need, privacy, capabilities needed) are stable. The learner fills in whichever model fits the recommended tier at the time they're using the card.

**It should live somewhere the teen will actually find it.** Recommend the module writer suggest: save it as a note on their phone, pin it in the chat tool, or paste it at the top of a recurring notes doc. A scorecard that lives only in the course portfolio gets forgotten.

---

## 5. Teen-relevant example

**The "used the fast model for a task that needed careful reasoning" scenario is the strongest candidate.** It's the most common real pattern, and it produces a failure mode that's subtle but clear — not a crash, but a quietly wrong answer that looks fine at first.

### Constructed scenario (grounded in real observed patterns)

**The situation:** A teen is writing a persuasive essay arguing that their school's cell phone ban is counterproductive. They're in a hurry and use the quick/free-tier model (Haiku-equivalent). They ask: "Give me three strong arguments against a school cell phone ban."

The model gives three arguments — fluently written, plausible, easy to include. The teen uses them without rethinking.

**What they got:** generic arguments ("phones can be used for educational purposes," "bans don't address the root cause of distraction"). Not wrong, but shallow and easy to counter in class debate. No citations, no nuance, no engagement with the strongest version of the opposing view.

**What a heavier model or reasoning mode would have done differently:** spent more effort on the actual quality of the argument. With an explicit prompt to reason carefully, a heavier model is more likely to: identify which arguments are actually the strongest (not just the most obvious), note where counterarguments are particularly strong and pre-address them, and flag that the teen should verify the claim about educational use with a real study or example. The output would be harder to counter and more useful for a real debate.

**The teaching moment:** the fast model didn't fail in an obvious way. It gave plausible-looking arguments. The failure was quiet — the arguments would have *worked* for a low-stakes context but would have fallen apart under scrutiny. That's exactly the "wrong tool for the job" failure pattern: not a crash, but a quietly lower ceiling.

**Why this is better than a catastrophic failure story:** it mirrors real usage. Most teens won't use AI and get complete nonsense. They'll use AI and get something that's *fine*, and miss that "better" was available. The module's job is to raise that ceiling by teaching them to notice when they're leaving quality on the table.

### Variant: the "trusted one impressive answer" failure

Secondary scenario worth having in the writer's back pocket: a teen asks a complex chemistry question, gets a confident and beautifully formatted answer from the first model they try, and doesn't test it with a second model or reasoning mode. The answer has a subtle error in step 3 of a 5-step problem — the kind of error that a reasoning model would have caught by checking its own work but a standard model let slide because it was predicting plausible-sounding steps, not actually solving the problem. The teen submits it. The error is caught by their teacher.

This variant directly illustrates the "test two options instead of trusting one impressive answer" principle in the module spec. Keep it as an optional second example, after the essay scenario lands the main point.

---

## 6. Real business example

**The strongest documented case for this module is the enterprise AI model routing / cost-quality tradeoff space, which is well-documented from 2024–2026. The cleanest and most teen-accessible version:**

### The "routing" pattern — organizations learned to stop sending everything to the big model

By 2024–2025, a well-documented operational pattern emerged across companies using AI at scale: organizations that initially routed *all* queries to their most capable (and most expensive) model found this was both slow and costly. The better-performing teams built "model routing" systems — automatically sending simple questions to a fast/cheap model and only escalating to a heavy model when the task actually needed it.

**Concrete and reported:** Anthropic's own documentation and multiple published case studies (e.g., from Klarna, from various legal-tech and customer-service automation companies) describe explicit tiering as a cost/quality optimization. Klarna's widely-reported 2024 AI deployment (customer service automation) is the most cited public example — but the specific model-selection lesson isn't the customer service automation itself; it's that the teams doing it well distinguished between tasks that needed careful, nuanced handling (escalated to humans or heavier AI) and tasks that could be handled by simpler automation. The ones who didn't make that distinction got worse outcomes on both cost and quality.

**How to frame it for a teen:** "Real companies figured out the same thing you're learning: not every task needs the biggest model. Teams that sent everything to the expensive, heavy AI found it was slow and blew their budget. Teams that matched the model to the task got better results on the complex stuff *and* didn't waste money on the simple stuff. It's the same principle you're applying — just at a bigger scale."

**A second, more specific example (better documented for accuracy):** in 2025, multiple AI developer blogs and engineering teams published explicit comparisons of "GPT-4o vs. GPT-4o-mini" (or Claude Sonnet vs. Haiku, or Gemini Pro vs. Flash) for specific tasks, finding that for classification, summarization, and simple Q&A, the smaller model matched the larger model's quality at a fraction of the cost and latency. For complex reasoning tasks (multi-step logic, code with multiple interacting parts, legal analysis), the larger model was measurably better. The principle became a standard recommendation in AI engineering: "use the smallest model that meets the quality bar for the task."

**Flag for owner:** I cannot verify the exact Klarna case details live in this research pass — the pattern is widely reported in AI press and engineering communities, but the specific numbers (how many agents, what the cost savings were) should be checked before using in learner-facing copy. The principle itself (model routing / matching model to task tier) is solidly documented and safe to teach.

**Recommended framing for the module:** don't name a specific company unless the owner can verify the detail. Instead: "Companies discovered this the hard way — early AI teams sent every task to the most powerful (and slowest, and most expensive) model they had. The teams that did best learned to route: easy tasks to a fast model, hard tasks to a heavy one. They got better results on the hard stuff and stopped wasting time on the easy stuff. That's model selection at work."

---

## 7. Go Deeper references

**Critical constraint from the Master Build Plan:** "this content ages fast — keep it principle-based plus a separately maintained cheat sheet." Go Deeper links for Module 4 should therefore point to principle-based, non-leaderboard sources. Benchmarks and rankings (LMSYS Chatbot Arena, Hugging Face Open LLM Leaderboard) age immediately and should not be the primary Go Deeper — if they're listed at all, label them explicitly as "fast-moving, check for current rankings."

### Recommended references (verify live before publishing)

**1. Simon Willison — "Everything I know about LLMs" (and related blog posts on model selection)**
URL to check: https://simonwillison.net
Willison is a credible, independent AI commentator (no vendor affiliation) who writes accessibly about practical model use. His posts consistently take a "what's the actual practical difference" approach rather than benchmarking. Specifically useful for Module 4: his ongoing commentary on when smaller models are good enough and when they're not. The specific post URL to find: search his site for "model selection" or "when to use a smaller model." His writing is teen-accessible (plain English, concrete examples). Flag: no single canonical post to link — recommend the module writer find the most relevant 2025–2026 post from his blog at research time.

**2. Anthropic — "Models overview" (official, vendor docs)**
URL: https://docs.anthropic.com/en/docs/models-overview (verify live)
Rationale: Anthropic's own documentation describes the Opus/Sonnet/Haiku tiers and their intended use cases — this is the primary source for what the provider itself says each tier is for. Not a ranking; a use-case description. Will stay relatively current (Anthropic updates it as models ship). De-vendor caveat: link this as "Claude's own description of its tiers — other providers have similar docs"; pair it with an OpenAI or Google equivalent so it doesn't read as Claude-first.

**3. OpenAI — "Model overview" or "Which model should I use?"**
URL to check: https://platform.openai.com/docs/models (verify live)
Same rationale as above — primary source, use-case descriptions, not a leaderboard. Pair with the Anthropic link.

**4. "Choosing the Right LLM for Your Use Case" — non-vendor principle article**
Recommend the module writer find a current (2025–2026) non-vendor explainer on this topic. Good candidates to look for: a post from a credible independent source (Towards Data Science, O'Reilly, MIT Technology Review, or a well-regarded independent AI engineer). The ideal piece focuses on *criteria for choosing* (not a ranked list of winners) and is written for a general technical-adjacent audience (not ML researchers). Search query: "how to choose an AI model for your task criteria 2025 2026" and filter for non-vendor, non-SEO-content-mill results.

**Note: explicitly do NOT link LMSYS Chatbot Arena, Hugging Face leaderboard, or any benchmark ranking as the primary Go Deeper** for Module 4. These change weekly and teach the wrong lesson (compare scores, not match task to capability). If a curious teen asks "but which model is technically best right now?" — that's fine to acknowledge in a caption: "For current rankings, Chatbot Arena at lmsys.org or the Hugging Face leaderboard are the go-to sources — just know they change frequently and don't tell you which model is right for *your* task."

---

## 8. Open questions / judgment calls

These need owner sign-off before drafting the module.

**Q1: Should the Core name specific model families, or stay fully generic?**

The tradeoff:
- Naming Claude/GPT/Gemini (family names, no version numbers) makes the module feel concrete and current. Teens are using these tools by name and it would feel evasive not to mention them.
- Staying fully generic ("a fast model," "a heavy model") is more durable but may feel abstract, especially in the Guided Lab where the learner needs to actually pick two tools to compare.

**Recommendation:** name the family names (Claude, ChatGPT, Gemini) as examples of tools in each tier, exactly as Module 2 does — but use the tier label (fast / standard / heavy) as the primary vocabulary, not the brand name. The lab can say "pick two tools you have access to — could be Claude and ChatGPT, or two tiers of the same tool (like Haiku and Opus)." This matches the Curriculum's de-vendor guardrail while still being concrete.

**Q2: Should the lab compare two providers, or two tiers of the same provider?**

Arguments for two providers (e.g., Claude vs. ChatGPT):
- More dramatic visible difference in style, tone, default behaviors
- Reflects the real-world choice more teens face (they may have both free tiers)
- More interesting — different "personalities"

Arguments for two tiers of the same provider (e.g., Haiku vs. Opus):
- Cleaner isolation — everything is the same except the tier, so quality differences are easier to attribute
- More reliably available (a teen with one account can still do it)
- More directly teaches the "tier" principle

**Recommendation:** design the lab to work either way, with a note that explains both options. Primary instruction: "pick two tools you have access to — different apps, or two tiers of the same app if one of them offers that." Don't prescribe one setup; the principle is the same.

**Q3: How opinionated should the scorecard be about which criteria matter most?**

The current scorecard design (Section 4 above) weights the four criteria equally. An alternative: make task complexity the dominant criterion (it almost always drives the answer) and treat the others as modifiers.

**Recommendation:** keep the four-question flow as designed — it naturally puts task complexity first, which means it effectively weights it highest without making the other three feel like afterthoughts. The owner may want to add a tiebreaker line: "If the scores are equal: default to the faster model. You can always escalate."

**Q4: Should the module include a "cheat sheet" as a separate, separately maintained artifact?**

The Master Build Plan explicitly calls for "a separately maintained cheat sheet" for this module, acknowledging the content ages fast. The research notes cover the principle-based module content. But the cheat sheet (which specific model is in which tier right now, what costs what, what's free-tier vs. paid) is a separate maintenance burden.

**Recommendation:** design the Core module to be fully principle-based (tiers, criteria, lab) and create the cheat sheet as a *Codex* document that lives in Go Deeper — updated by the course owner quarterly. The module itself should reference it: "For a current list of which tools are in which tier (it changes), see the Model Landscape cheat sheet in the Codex." This separates the stable (the module) from the fast-moving (the rankings/costs), exactly as the Master Build Plan intends.

**Q5: Does the Guided Lab need an in-module sandbox, or can it live outside (in whatever tool the teen already uses)?**

Format-and-Delivery.md specifies that labs happen "in the built-in AI sandbox." But Module 4's lab is explicitly about comparing two different tools — which by definition can't both live in a single sandbox.

**Recommendation:** flag to the owner that Module 4's Guided Lab is likely an exception to the sandbox model. The learner needs to open two tabs (or two tools) and run the same prompt in both. The module player can still host the scorecard and the prompt template; the actual AI interaction happens externally. This needs owner awareness, as it's slightly more friction than a standard sandbox lab.

**Q6: How should the module handle the teen who only has access to one tool?**

Not every learner will have two AI accounts or two tier options. The lab as designed benefits from comparing two things.

**Recommendation:** add a one-sentence fallback: "If you only have access to one tool: try the same prompt with and without reasoning mode (if your tool offers it), or with a very different system prompt ('you are an expert tutor' vs. no setup). It's not a perfect two-model comparison, but it still builds the habit of testing before trusting."

---

*End of research notes — Module 4. Next step: module writer drafts using these notes as the brief.*

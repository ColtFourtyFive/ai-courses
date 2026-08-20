# Research Notes — Module 0: Start Here: Demystify

> Research pass for Module 0 only. Not prose, not the module. Notes for the module writer.
> Owner: Ayan. Output of research brief in `research-briefs/module-00-research-brief.md`.

---

## 1. Concept check — the micro-framing that opens the course

### What Module 0 needs (and doesn't need)

Module 0 is almost entirely Mission — the spec is explicit: "no theory first." But it still needs a one- or two-sentence opening frame that does one specific job: give the learner permission to start without understanding anything yet, while making them curious about what they're about to do.

The framing can't:
- Explain what AI is (that's Module 1)
- Hype ("AI will change everything!") — this audience has heard that, and many are suspicious of it
- Reassure through facts — that just delays the actual de-risking, which only the build itself can do
- Sound like a disclaimer or warning

The framing needs to:
- Signal: you're going to build something, right now, before we explain anything
- Imply: the wall you thought was there is not actually there
- Create mild curiosity/anticipation without promising something they then have to wait for

### How build-first course openers work

The "build first, explain later" model has a documented track record in technical education. The clearest analogous examples come from:

**Scratch (MIT Media Lab, ~2007 onward).** Scratch was designed around the premise that kids should make something in the first session before any concept instruction. The documented emotional arc: first-session creation produces ownership ("I made that"), which lowers the affective filter enough that concept instruction in later sessions actually lands. The research behind it (Resnick's "hard fun" principle) found that the feeling of authorship — even over something small and imperfect — is the most effective anxiety-reducer, more so than reassurance or explanation. Key finding for Module 0: the artifact has to be genuinely theirs, not a pre-built demo they just clicked "run" on. The difference between "I watched it happen" and "I described it and it appeared" is the whole thing.

**CS50 (Harvard, David Malan).** CS50's opening week sends students away having run a working program on day one, before loops or variables are explained. The documented instructor observation: students who would otherwise drop in week 2 (because concepts feel abstract) stay because they already have a working thing and feel ownership. Framing used: "Here's a program. It works. You made it work. We'll explain why later." No promises about how smart it is, no "isn't this incredible," just — it works and you made it.

**"Build first" in AI workshop contexts.** Multiple documented AI literacy workshops for non-technical adults (MIT Media Lab's "AI + Art" series; various Art + AI workshops) open with a generation task before any technical content — ask the AI to make something for you, watch it appear. Facilitator accounts consistently note the same emotional beat: surprise, then ownership, then questions ("but how does it know?"). The questions are the signal — they indicate the fear has converted to curiosity. Module 0 is designed to produce exactly this.

### Candidate one-liners / micro-framings

These are draft candidates for the writer to evaluate. They are in roughly increasing order of risk/boldness. All assume the framing appears immediately before the Mission block, not before anything else.

**Option A (permissive/simple):**
> "No setup. No experience needed. Describe something you want, and watch it get made. Questions after."

Evaluation: Very clean, very low-pressure, no implicit threat. Slightly cold — may not carry enough warmth/personality for a 13-year-old who is nervous.

**Option B (the-wall-is-smaller framing):**
> "The first thing most people think when they hear 'AI' is: 'that's not for me.' You're about to find out that was wrong."

Evaluation: Slightly confrontational in a good way — uses the expected fear as the hook. Risk: could feel presumptuous if the learner isn't actually nervous. But this is the target audience, so it fits. The word "wrong" does real work here. Directly echoes the Curriculum.md framing ("the wall is gone before we explain anything").

**Option C (the course arc in one sentence — recommended):**
> "Every lesson after this one explains how AI works. This one just shows you that you can use it — right now, today, before you know any of that."

Evaluation: This is the strongest option for the course arc function. It explicitly tells the learner that Module 0 exists *apart* from the explanation sequence, which removes the "I need to understand this before I can do it" assumption. It also previews the arc (you'll understand it eventually) without requiring them to believe that upfront.

**Option D (ultra-short hook):**
> "Before the explanation: just make something."

Evaluation: Works if the product design gives it visual weight (large type, prominent placement). Might be too sparse if it's one line of body text in a block. Needs design support to land.

**Option E (the fear-to-authorship pivot):**
> "AI tools feel unfamiliar. The fastest way to fix that isn't reading about them — it's making something with one, right now."

Evaluation: The most explicit about the pedagogical logic, which might be useful for nervous learners who want a reason to trust the "jump in" instruction. Slightly more words than the others. Clean.

### Recommendation

**Option C** is the strongest for the course arc function — it correctly signals "this module is different from all the others" and removes the prerequisite assumption without over-explaining. **Option B** is a strong second if the voice needs more edge/personality. The writer might consider combining them: Option B as an opening beat, Option C as the follow-on sentence that lands the instruction.

What to avoid: any version of "AI is amazing" or "don't be scared" — both are counterproductive. "Don't be scared" names the fear explicitly (making it bigger) and then fails to address it through action.

---

## 2. The 5-minute unlock build — candidate evaluation

### The design criteria (from the brief)

The unlock build must be:
1. Achievable in under 5 minutes, with a working result
2. Jaw-dropping — the output surprises them
3. Dead-simple — no setup, no accounts beyond the AI tool, no code, no configuration
4. Personally relevant — they care about the output, not just the fact that it appeared

On criterion 3 specifically: the module needs to work for someone who has never opened an AI chat tool. The first instruction can be "go to [tool], make a free account, open a new chat." That's acceptable setup. What can't be required: installing anything, getting API access, configuring a tool, uploading files, or needing to have done something prior to this module.

### The "jaw-dropping" problem — what actually creates the wow

The wow factor in a first AI experience almost never comes from the AI doing something technically impressive. It comes from:
- **Speed:** something that would take them 30+ minutes to write appearing in 10 seconds
- **Personalization:** it used their specific detail (their name, their game, their situation) and the output is clearly *about them*
- **Unexpectedly good quality:** it's better than what they would have written themselves
- **The prompt-to-output gap:** they gave a vague-ish description and something polished appeared

The builds that consistently produce this response are the ones where the output is both personally relevant AND something they would recognizably have trouble producing themselves (a poem, a story in a specific voice, a structured plan, a quiz with good wrong-answers).

### Candidate builds — evaluated against all four criteria

**Candidate A: Custom quiz on their favorite game, show, sport, or topic**

- *How it works:* Prompt: "You're a trivia quiz host. Create a 10-question quiz about [Minecraft / Taylor Swift / Premier League / anything they love], with 4 multiple-choice options per question and the answers at the end. Make the wrong answers good — plausible but clearly wrong if you know the topic."
- *Wow factor:* High, especially for topic-passionate teens. The wrong answers are what creates the wow — the AI "knows" the topic well enough to make plausible wrong options, which signals real knowledge and makes the quiz actually fun to take.
- *Simplicity:* Maximum. One prompt, one output. No setup beyond an AI chat. Works on any AI chat tool.
- *Personal relevance:* High — they pick the topic, so the output is immediately theirs. They'll want to share it or test their friends.
- *Time estimate:* 2–3 minutes including picking the topic.
- *Risk:* Low, but the wow can fall flat if the AI picks obscure facts from their topic. Mitigation: tell them to add "use well-known facts, not obscure ones" to the prompt. Also, a teen who doesn't have a strong topic passion might not feel the wow — they'll need a fallback topic if they're not sure what to choose.
- **Verdict: Strong pick for the primary unlock build.** High on all four criteria. Shareable, re-playable. Works well as a social artifact too ("try this quiz I made").

**Candidate B: Rewrite your texts in a different tone**

- *How it works:* Prompt: "Rewrite this text message as if I'm [a pirate / a Shakespearean character / a 1950s radio host / extremely passive-aggressive / excessively formal]: [paste a casual text they'd actually send]."
- *Wow factor:* Medium-high. The humor factor is high ("this is hilarious") but the surprise factor is lower because it's closer to a well-known "AI thing." Teens may have already seen this type of prompt on TikTok or social.
- *Simplicity:* Maximum. One prompt, instant output.
- *Personal relevance:* Medium-high — they write the source text, so it's theirs. But the output is about a text they wrote, not about something they care about as a subject.
- *Time estimate:* 1–2 minutes.
- *Risk:* Risk of "I've seen this before" from a teen who is even slightly familiar with AI. The wow is lower because the task is "fun" rather than "impressive." May be better as a second build option than the primary unlock.
- **Verdict: Good secondary option.** Works if Candidate A doesn't land for a particular learner. More playful, less impressive. Probably not the primary unlock unless the module explicitly wants humor as the vehicle.

**Candidate C: A short poem or rap about the learner themselves**

- *How it works:* Prompt: "Write a short rap verse (8–12 lines) about me. Here are the facts to use: my name is [name], I'm [age], I love [interest], I'm good at [skill], and I find [thing] really annoying. Make it sound like a real rap — good flow, rhymes, a bit of attitude."
- *Wow factor:* High, specifically because of the personalization AND the quality bar. A good rap has rhythm, rhyme scheme, and attitude — when the AI actually delivers on all three, with their own details woven in, the gap between "I described myself" and "this polished thing appeared" is genuinely surprising.
- *Simplicity:* Maximum.
- *Personal relevance:* Very high — it's literally about them, their name, their interests.
- *Time estimate:* 2–3 minutes including filling in the personal details.
- *Risk:* The wow depends on the output quality. A mediocre rap (poor rhyme scheme, stilted) kills the moment. Mitigation: the prompt engineering matters a lot here — "good flow, rhymes, a bit of attitude" does real work. May also feel awkward for teens who find the whole thing cringeworthy rather than fun, depending on personality. Gender/personality fit: this skews toward learners who are comfortable with self-expression and humor about themselves. Not universal.
- **Verdict: Strong pick, but slightly narrower audience than Candidate A.** The personalization factor is the highest of all candidates, which is a genuine advantage. If the module offers a menu of build options, this is a strong inclusion.

**Candidate D: A one-paragraph story opening in a style they pick**

- *How it works:* Prompt: "Write the opening paragraph of a story in the style of [Harry Potter / a horror story / a nature documentary narrator / a sports commentary / anime] where the main character is a [student at a school for dragons / detective who can smell lies / person who woke up speaking every language except their own]. Just the opening paragraph — make it gripping."
- *Wow factor:* High. The style + premise combination consistently produces something that reads like professionally published genre fiction. The surprise is that they named something absurd and it came back polished.
- *Simplicity:* Maximum.
- *Personal relevance:* Medium-high. They picked the style and premise, but it's not *about* them. The "I made that" feeling comes from authorship of the idea, not from their personal details appearing.
- *Time estimate:* 3–4 minutes with time to think of a premise.
- *Risk:* Lower-than-expected wow if the premise is generic (mitigated by guiding them to pick something weird). Some teens may not have a strong opinion about style — the menu of style examples helps.
- **Verdict: Strong pick, especially for creatively-oriented teens.** Complements the quiz option — quiz is for topic-passionate teens, story is for creatively-inclined ones. Good menu item.

**Candidate E: "What should I do about [situation]" life advisor**

- *How it works:* Prompt: "I'm dealing with a situation: [describe it briefly — a friend conflict, an awkward group project situation, not knowing what to pick for a birthday gift for someone]. Give me three different ways I could handle it — one very direct, one very indirect, and one creative/unexpected. Be honest about the trade-offs."
- *Wow factor:* Medium. The output quality is high (AI is good at this), but the wow depends on whether the advice is actually useful or surprising. Teens may be skeptical about AI giving life advice ("it doesn't know me").
- *Simplicity:* Maximum.
- *Personal relevance:* Very high if they use a real situation.
- *Time estimate:* 2–3 minutes.
- *Risk:* The "I don't trust it to know me" objection is real and valid — this build surfaces it directly. That might actually be a feature (it raises the healthy skepticism early), but it risks turning the first experience into a "meh, it doesn't really get my situation" reaction rather than a wow. Better as a Module 3 or Module 5 illustration. **Not recommended as the primary unlock.**
- **Verdict: Weaker for Module 0, better for later modules.** The wow requires trusting the output, which nervous first-timers haven't earned yet. Reserve for after Module 3's capabilities/limits discussion.

**Candidate F: A personalized study plan**

- *How it works:* Prompt: "I have a [history / math / biology] test in [X days]. I need to cover: [list 3–4 topics]. I study best by [doing practice problems / reading summaries / making flashcards / talking through concepts]. Create a day-by-day study plan for me."
- *Wow factor:* Medium. Useful but predictably useful — it's easy to imagine "a study plan generator" before the build, which undercuts the surprise.
- *Simplicity:* Maximum.
- *Personal relevance:* High — grounded in their actual school situation.
- *Time estimate:* 3–4 minutes.
- *Risk:* The output feels useful rather than surprising. The "I made that" moment is weaker because the output doesn't feel creative or unexpected. Teens who are skeptical of AI as a school tool may dismiss this quickly ("my teacher would just say to study harder").
- **Verdict: Weaker for Module 0's jaw-dropping requirement.** Better as a Module 6 (Grounding/Context) or Module 5 (Prompting) example, where the frame is "here's how to get AI to be useful for actual school."

### Summary recommendation: offer a menu of 3 options

Do not pick one single build. Based on the above, a menu of 3 options serves the Module 0 goal better than a single fixed build, for two reasons:
1. Personal relevance is the hardest criterion to guarantee with a single build — it depends on who the learner is.
2. The "they picked it" ownership is itself part of the wow. A learner who chose their own build has more investment in the output than one who was assigned a build.

**Recommended menu:**

| Option | Prompt type | Best for | Wow driver |
|---|---|---|---|
| **A: Custom quiz** | "Make a 10-question quiz about [their topic]" | Topic-passionate teens | It knows their topic well enough to make good wrong answers |
| **C: Rap/poem about me** | "Write a rap about me using these facts" | Self-expressive teens | It's *about them*, and it's polished |
| **D: Story opening** | "Write the opening of a story in [style] where [weird premise]" | Creative/fiction-curious teens | It treated their absurd premise as real and made something good |

**Framing the menu choice:** Give each option a one-sentence description that names the type of learner it fits, so the teen can self-select quickly. Example: "Pick the one that sounds most like you." Then give them a ready-to-use prompt template for whichever they choose, so they're not writing the prompt from scratch.

**One fixed option as a fallback:** If the module can't present a menu (e.g., product design constraints), the custom quiz (Candidate A) is the strongest single pick because it works across the broadest range of teen interests.

---

## 3. Teen-relevant examples — documented "wait, I made that?" moments

### What the research and press record actually shows

A single clean, citable, "first-time teen builds with AI" moment with a named teen and specific quote is hard to find in the public record, for the same reason as Module 1: we don't cite specific named minors for something this informal, and most documented cases come from educator accounts rather than the teens themselves. What exists is a strong pattern across multiple educator accounts.

**The educator-account pattern (well-documented, multiple sources):**

The most consistent account in AI literacy educator writing describes a specific arc in first-session workshops:

1. Teen starts skeptical ("this is just autocomplete" / "I don't want to get in trouble" / "my teacher will know")
2. Facilitator gives a simple prompt template (not a blank text box — the blank text box freezes nervous beginners)
3. Teen fills in their own details and submits
4. Output appears
5. Teen reads it — brief silence — then one of two reactions: "that's actually really good" or "[reads it aloud to neighbor]"
6. Questions start: "can I ask it to do [x]?" — the shift from nervousness to experimentation

The "reads it aloud to neighbor" moment is the documented signal that the wow landed. It means they want to share what they made, which indicates ownership.

**Specific educator accounts and contexts:**

- Ethan Mollick (Wharton professor, "One Useful Thing" Substack) has written extensively about first-time AI experiences with students who arrive skeptical. His documented observation: the single most effective de-risking intervention is asking students to do something with AI that they had already planned to do without it — write something, plan something, explain something — and seeing the output. "The visceral experience of working with AI is worth more than any description of it." This matches Module 0's design exactly.

- AI literacy workshops documented in educational press (EdSurge, Edutopia, 2024–2025) consistently describe first-session introductions where students are asked to make something — a poem, a short story, a game concept — before any technical explanation. Reported observations: students who initially say "I don't know what to ask it" become more engaged once they have a template (the blank-box freeze is real and documented); students often share outputs with each other without being prompted to.

- "AI in Education" practitioner accounts (various, 2024–2025) describe specific moments that produced visible surprise: when a student asked about a very niche hobby or fandom topic and the AI responded with detailed, accurate knowledge. The surprise comes from "it knew about that" — it felt like the AI was reading their specific interests.

**A useful composite scenario for the module (not a single incident, constructed from the documented pattern):**

*"First time Priya opened an AI chat, she typed a quiz about competitive Pokémon battling — EV spreads, tier rankings, the stuff most people don't know exists. She expected something generic. What came back was specific, accurate, and had genuinely tricky wrong answers. She looked up from her screen and said: 'how does it know this?'"*

This represents what actually happens in well-documented first-contact situations. The "how does it know this?" question is the signal. It's the exact moment the fear converts to curiosity, which is the emotional target.

### The blank-text-box problem — documented and important for block design

Multiple facilitator accounts note the same friction point: when beginners are told "just try it — type something," a significant portion freeze. The blank text box triggers anxiety because the learner doesn't know what "right" looks like. This directly affects Mission block design for Module 0. The fix, consistently documented: give a prompt template with fill-in-the-blank sections, not a blank box. The learner fills in their specific details, submits, and has an immediate working result. This is the difference between a Mission that works and one that stalls.

---

## 4. The reframe line — the one thing to know before diving in

### What it needs to do

The module needs a short statement (1–3 sentences) that reframes what AI is before the learner dives in. Not a lecture — the spec is clear: "more like 'here's the only thing you need to know right now.'"

The reframe line is not a definition of AI. It's a mental permission slip.

### What the Curriculum.md draft already does

The Curriculum.md draft says:

> "Before any theory, you'll build one small, real thing — so the wall is gone before we explain anything."

And:

> "That's the whole point — you just made something by describing it."

These are good. They're honest about the approach and they don't oversell. The "wall is gone" framing is strong — it acknowledges there was a perceived wall without dwelling on the fear.

### What's missing from the current draft

The current Curriculum.md draft doesn't have a reframe for *what AI is* at the start of Module 0. It has an approach statement ("build before explaining") but not a one-sentence mental model the learner can hold while doing the build. That mental model doesn't need to be technically accurate — it needs to be accurate enough to get them through the next 15 minutes without confusion.

### Candidate reframe lines

**Option 1 (the simplest):**
> "AI chat tools work like a very well-read assistant who responds to whatever you describe. You're going to describe something. It's going to make it."

Evaluation: Functional. Extremely low bar — anyone can follow that instruction. "Very well-read assistant" is a scaled-down version of the Module 1 "brilliant intern" analogy, which is intentional — Module 1 gets the full analogy; Module 0 just needs enough to proceed. Risk: "assistant" could imply a helper who needs exact commands, which isn't quite right.

**Option 2 (the description-to-output framing — recommended):**
> "The only thing you need to know right now: AI tools respond to plain-English descriptions. You describe what you want. A result appears. That's it."

Evaluation: Strongest option. It correctly captures the mechanism without explaining it, and it implicitly addresses the "I don't know how to use it" anxiety by reducing the interface to: describe something, get a result. "Plain English" is important — it's the reassurance that no special syntax or knowledge is required. Directly actionable.

**Option 3 (the you-already-know-how framing):**
> "You already know how to do the thing that makes AI work: you describe what you want. That's the whole skill. Let's try it."

Evaluation: Strong on confidence-building. The "you already know how" frame is psychologically important for nervous first-timers — it reframes the tool as an extension of something they can already do (describe things) rather than a new skill to learn. Slightly cocky in a good way. Works well if the module's tone is dry/confident rather than warm/nurturing.

**Option 4 (the "no wrong answer" permission):**
> "There's no wrong way to start. You type something, it responds. If you don't like what you get, you try again. That's genuinely the whole game."

Evaluation: Good for anxiety-reduction specifically. The "no wrong way" frame is effective for the most nervous learners. Risk: might undersell the eventual skill of good prompting (which becomes Module 5). Better as a secondary reassurance within the Mission block instructions than as the primary reframe.

### Recommendation

**Option 2** as the reframe line. Optionally followed by Option 4 as the anxiety-reduction beat within the Mission block itself.

The Curriculum.md framing ("so the wall is gone before we explain anything") should stay — it belongs in the "why this matters" section, not the reframe line itself. These are different jobs: the Curriculum framing explains the module's design; the reframe line gives the learner what they need to take action right now.

---

## 5. Interactive block design — what makes a guided Mission work for nervous first-timers

### Should it offer a menu or a single fixed build?

**Answer: menu, strongly.** See Section 2 above for the full argument. The short version: personal relevance is the highest-leverage factor in whether the unlock build creates the "wait, I made that?" moment, and personal relevance requires the learner to have made a choice that reflects something about them. A fixed build can produce a cool output but it doesn't feel like *their* output.

However, the menu should be tight (3 options max), and each option should have a complete, ready-to-use prompt template. The learner shouldn't have to construct the prompt — they fill in the blanks in a template and submit. This is the documented fix for the blank-text-box freeze.

### What does "success" look like for this block?

The brief asks: "is it the artifact itself, or the emotional reaction?"

**Answer: the emotional reaction, operationalized through sharing.** The artifact is the mechanism; the emotional reaction is the actual outcome. Success criteria for the Mission block are not "learner produced a quiz" but "learner produced something they wanted to show someone else."

The practical success signal in a classroom or cohort context: did they share it? Did they read it aloud? Did they immediately ask "can I try another one?" These are behavioral proxies for the emotional reaction.

In a self-paced, async product context, the success signal has to be built into the design: the module should prompt the learner to share their output to the cohort feed after completing the build. That's the Module 0 artifact — not a polished thing, but a first-thing-they-made, posted with a short caption. The act of posting is the proof that they felt ownership.

### What's the right amount of guidance vs. openness?

The documented sweet spot for nervous first-timers:
- **More guidance on the prompt structure:** give them a template, not a blank box
- **More openness on the content:** they fill in the part that's about them
- **One example of a complete prompt** so they can see what "good" looks like before they submit
- **No instructions on what to do with the result** — the reaction should be unscripted

In pedagogical terms: guided scaffold for the tool interaction, open canvas for the content. The learner should feel they made a creative choice; they shouldn't feel they're following a recipe.

### What the Mission block instructions should include

Based on the documented "build-first" format that works:
1. "Pick one of these" (the 3-option menu, each with a one-sentence descriptor)
2. "Here's your starting prompt for [Option X]" (ready-to-paste template with [FILL IN YOUR THING] highlighted)
3. One example of a completed prompt and its output (so they can see the gap between simple input and polished output — this is the preview of the wow)
4. "Submit it. Read what you get. You made that."
5. Optional: "Want to change something? Just tell it." (introduces iteration without requiring it)
6. "Share your output below." (or cohort feed / show-and-tell mechanic, per Format-and-Delivery.md's social layer)

No step-by-step instructions for how to use the AI tool itself — that introduces friction. The instruction is just "go to [tool name], start a new chat, paste the prompt."

### Documented examples of build-first course openers that worked

**CS50 (Harvard).** Week 1 assignment: run a pre-written C program, change one thing, see what happens. By end of week 1, every student has made a working program run. The course deliberately delays "how does C compile" until the student has the experience of it working. Outcome: dramatically higher retention through the first month compared to courses that front-load theory.

**Scratch (MIT/elementary).** First session: make a sprite move. No instruction on variables or loops — just: make it do something. Resnick's documented finding: students who make something in the first session are significantly more likely to return in the second.

**"Making is believing" principle (constructivism, Piaget/Papert).** The pedagogical basis for all of these: understanding is constructed through doing, not through being told. Papert's specific contribution: making for an audience (showing the thing you made to someone) is more powerful than making for yourself. This is why the Share block matters even in Module 0.

**Directly relevant AI precedent:** Multiple AI literacy curricula (MIT Raise's "AI + Ethics" curriculum for middle schoolers; Day of AI; Google's "Teachable Machine") open with a hands-on activity before any definition. Consistent facilitator observation: the definition lands better *after* the experience because learners have something concrete to attach it to. This is the strongest research-backed argument for Module 0's "no theory first" design.

---

## 6. Go Deeper references — candidates for Module 0

Module 0 is not a concept module, so the Go Deeper section should be minimal and serve a narrow purpose: reward a teen who just built their first thing and now wants to understand what just happened. It should not be the "here's how AI works" deep dive — that's Modules 1–3.

The question it answers for a Go Deeper in Module 0: "I just made something cool — where can I learn more about what I just did?"

### Candidate references

**Candidate 1: Ethan Mollick — "Working With AI: Two Paths to Prompting" (One Useful Thing)**
- URL: https://www.oneusefulthing.org/p/working-with-ai-two-paths-to-prompting
- What it is: A short, accessible blog post (Mollick's Substack, active and reputable) about the two basic modes of using AI — instructing it (like Module 0's unlock build) vs. iterating with it. Well-written, aimed at a general audience, not technical.
- Why it works for Module 0 Go Deeper: a learner who just did their first build and found it interesting will get a clear, readable next step that introduces the idea of iterating — which is Module 5's skill — without jumping into the full prompting curriculum.
- Verification note: Mollick's Substack is active and well-documented. The specific URL above is a known post title but could not be confirmed live (no web fetch access). Recommend owner does a quick manual check on the exact URL before publishing. The author and Substack domain (oneusefulthing.org) are definitively real and active.

**Candidate 2: MIT Raise — "How AI Works" (brief explainer aimed at students)**
- URL: https://raise.mit.edu/resources.html (resource hub)
- What it is: MIT's RAISE (Responsible AI for Social Empowerment) program has published accessible AI explainer resources including short videos and articles aimed at middle/high school students.
- Why it works for Module 0 Go Deeper: credible source (MIT), aimed at teens, short and accessible. Would reward a curious teen who wants the "so what actually happened when I made that quiz?" question answered at an introductory level.
- Verification note: MIT RAISE is real and active. The specific URL needs a manual check for current resource availability. The organization's existence and focus area are confirmed.

**Candidate 3: "How does ChatGPT work?" (OpenAI-authored intro, if current)**
- URL: https://openai.com/chatgpt/learn (or similar — OpenAI has published several intro-level explainer pages)
- What it is: OpenAI has maintained introductory "what is this and how does it work" content for general audiences. If current, this would be a vendor-authored but accessible explainer.
- Why it might work: directly connects to the tool a teen likely just used; authoritative source; usually kept accessible rather than technical.
- Concerns: vendor-authored (non-neutral), and OpenAI's site structure changes frequently. This should be the lowest-priority of the three candidates, and only used if the owner confirms a specific, stable URL is live and non-marketing-heavy. Skip if either condition isn't met.

### Overall Go Deeper recommendation for Module 0

Keep this section to 1–2 links maximum, consistent with the module's "no theory first, just build" design. The Go Deeper should satisfy the question "what just happened?" — not teach the full concept. A learner who wants the full concept will start Module 1. 

Best combination: **Candidate 1 + Candidate 2**, confirmed live by the owner before publishing. Drop Candidate 3 unless a specific non-marketing page is confirmed.

---

## Open questions / needs owner's judgment

- **Menu vs. fixed build:** if the platform can only present one build in the Mission block (e.g., due to product design constraints), pick **Candidate A (custom quiz)**. If the platform supports a choice menu, present all three recommended options. This is a product design question as much as a curriculum question.

- **Tool recommendation — RESOLVED since this research was written:** Codex is the locked starting platform, leading from Module 0 (per Master-Build-Plan §2.4), with Claude also shipping as a primary tool throughout. This entry originally weighed Claude.ai/ChatGPT/Gemini as candidates before that decision was locked; kept here for the research trail, but superseded. Follow-on implication this research pass didn't cover: Codex outputs code/diffs, not a hosted live preview, which changes what the Module 0 build instructions need to look like (see the module file's Owner notes).

- **The "share your output" step:** Module 0's artifact is "a working thing, made day one." For an async/self-paced product, the share mechanic needs to be designed into the platform (a cohort feed, a screenshot submission, etc.). If that mechanic isn't built yet, the module can still work — just make the artifact the prompt + output (copy-paste into a doc). The social layer (sharing) is important for motivation but not required for the emotional outcome to land. Flagging for the owner as a platform-dependency question.

- **Timing:** the brief says "~15–20 minutes." The Mission block as designed (pick option, fill template, submit, read, optionally iterate, share) fits comfortably in 10–12 minutes. The remaining time should be minimal-concept framing (see Section 1 and 4 above). This estimate assumes account creation is already done. If the learner has to create an account from scratch, add 5 minutes. Owner should confirm whether onboarding/account creation is out-of-scope for Module 0 or if it needs to be accounted for in the timing estimate.

- **Emotional target edge case:** the "wait, I made that?" moment doesn't land for every learner the first time. Some will feel "okay, it made something, so what?" — which is the learner who comes in with higher baseline confidence or has already used AI tools before. Module 0 needs a brief "what to do next" nudge for these learners: "already comfortable? Try changing one thing in your prompt and see what shifts." This is a gentle on-ramp to Module 1's Try-It design without requiring them to wait for Module 1. A one-sentence optional challenge within the Mission block handles this without slowing down anyone else.

- **Go Deeper URLs:** both Candidate 1 and Candidate 2 are from real, active sources but exact URLs need manual confirmation by the owner before publishing. Do not publish Go Deeper links without a live check.

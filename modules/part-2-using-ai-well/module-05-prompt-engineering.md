# Module 05 · Prompt Engineering: The Master Skill
**Owner:** Ayan  ·  **Status:** Ready to review  ·  **Emotional target:** "the power is in how I ask"
**Input from:** Osman  ·  **Research brief:** `research-briefs/module-05-research-brief.md`  ·  **Research notes:** `research-notes/module-05.md`

## Spec (from sources/Master-Build-Plan.md)
- **Covers:** prompting = clear thinking + communication (brief a brilliant intern); recipe — Role + Context + Task + Format + Iterate; a concrete before/after; techniques (examples, step-by-step, say what NOT to do, break into steps); the **operating brief** as the grown-up version; a good prompt makes output better, not *true*.
- **Input from Osman:** operating brief (*Advanced Codex*) + reusable prompt template (*Beyond Code*) — Source-Material-Library.md → Module 5.
- **Build new:** the foundational framing (drafted); the before/after Try-It; the Guided Lab that outputs a reusable prompt.
- **Blocks:** Concept · Try-It · Guided Lab · Share.
- **Artifact:** a reusable prompt they'll use for school this week.

---

# Module 5 · Prompt Engineering: The Master Skill
Emotional target: "the power is in how I ask"   ·   Est. time: ~35 min

## Why this matters
This is the highest-leverage skill in the entire course. The model's ceiling is high — your prompt decides how much of it you reach. Same model, vague prompt → mediocre output. Same model, sharp prompt → something you'd actually use. Once you get this, almost everything after it — custom assistants, agents — is mostly *this* skill applied.

## What you'll walk away able to do
- Write prompts that reliably get great output on the first or second try
- Explain why prompting is communication, not magic words
- Have a reusable prompt template you'll actually use for school this week

---

## Concept

### Prompting is not magic words

Forget prompt cheat sheets. Forget "jailbreaks." Forget any framing that treats prompting as a set of secret commands to unlock a machine.

**Prompting is clear communication.** The model is a brilliant intern who has read almost everything — but knows nothing about you, your class, your situation, or what you actually want. Your job is to brief them well. A good brief gets a good result. A vague brief gets a vague result — not because the model is dumb, but because it's doing its best with nothing to go on.

If you walked up to a new intern and said *"help me with my essay"* — they'd stare at you. What essay? What kind of help? For what audience? Due when? Same thing here.

---

### The five-piece recipe

Most strong prompts have these five pieces:

**1. Role** — who it should act as.
> *"You are a patient chemistry tutor."*

**2. Context** — the situation and what you already know or don't.
> *"I'm a 10th grader who missed the lesson on moles and has a quiz Friday. I understand what atoms are but the mole concept isn't clicking."*

**3. Task** — exactly what you want back.
> *"Explain moles using one everyday example, then give me three practice questions."*

**4. Format** — how you want it delivered.
> *"Keep it under 150 words. No jargon. Start with the example before the definition."*

**5. Iterate** — treat the first output as a draft, not a final answer.
> *"Good, but the example was about cooking — use something from sports instead and add one harder question."*

> A note on #5: the first four pieces go into your prompt. Iterate is what you do *after* you read the output. It's less an element and more a mindset — expect to refine, and you won't be disappointed by an imperfect first run.

---

### The fill-in-the-blank version

The full 5-piece recipe turns into a template you can actually copy. Here's the fill-in-the-blank version that covers the essentials in one block:

```
Create [output] for [audience].
The purpose is [goal].
Use the attached [source material] as the source of truth.
It should feel [three useful adjectives].
Include [requirements or constraints].
Show me a first version for review before publishing, sending, sharing, or changing access.
```

That last line — "Show me a first version for review before publishing, sending, sharing, or changing access" — is a habit worth building into every prompt where the output goes somewhere real. We'll return to it in Module 12, where it becomes especially important.

---

### See the difference

| | Prompt | What the model has to work with |
|---|---|---|
| **Weak** | "explain climate change" | Topic, nothing else |
| **Strong** | "You're a science teacher explaining to a curious 9th grader. Explain why climate change happens using one everyday analogy, in under 120 words, then check my understanding with two questions." | Role + audience + topic + analogy constraint + word limit + task structure |

Same model. Completely different output.

---

### A fully worked example

Here's what all five pieces look like assembled into a real prompt — something a teen could actually run right now:

```
ROLE: You are a patient history tutor who explains things through cause and effect,
      not just lists of facts.

CONTEXT: I'm a 10th grader preparing for a test on the causes of World War I.
         I understand that Archduke Franz Ferdinand was assassinated in 1914,
         but I genuinely don't understand why one assassination triggered
         a world war. I've read my textbook twice and it still doesn't click.

TASK: Explain the alliance system and why it turned a local conflict into a
      world war. Use an analogy I haven't seen before — not the falling-dominoes one.

FORMAT: Under 250 words. One paragraph on the alliance system, one on the chain
        reaction. End with two practice questions — one where I identify the
        alliance involved, one where I have to explain the logic of escalation.
```

Notice what this gives the model: a clear role, a specific situation, a well-scoped task with one deliberate constraint ("not the falling-dominoes one"), and a tight format with a specific ending. That's the recipe in action. Compare it to "explain WWI" and you'll see exactly why the output would be different.

---

### A few techniques worth knowing

**Show, don't just tell.** Give an example of what you want. Even one example dramatically narrows what the model produces toward what you had in mind.

**Ask it to think step by step** for anything involving logic, math, or multi-step reasoning. It genuinely improves accuracy on those tasks.

**Say what you *don't* want.** "Don't use bullet points. Don't add a motivational closing. Don't use the phrase 'it's important to note.'" Negative instructions are underused and highly effective.

**Break big asks into steps** instead of one giant prompt. One step at a time beats one giant "do everything" request almost every time.

**Ask for a draft before a final.** For any output you're going to submit, send, publish, or share — add "Show me a first version before I use this." This catches problems before they matter. It's not distrust; it's how a professional works. This is already baked into the fill-in-the-blank template above, and it's worth making it a habit everywhere.

---

### The one thing prompting can't do

A sharp prompt makes output *better*. It does not make it *true*. Module 3's verify habit still applies — better output is still output you should check when accuracy matters.

---

### Real stakes: why this matters beyond school

Some lawyers started using AI to write legal briefs without thinking carefully about their prompts. They'd ask it to "find supporting cases" — and it would confidently produce citations to cases that didn't exist. In 2023 (Mata v. Avianca, S.D.N.Y.), lawyers were fined and disciplined for submitting AI-fabricated citations they hadn't caught or verified.

The firms that avoided the problem weren't using a different AI. They were prompting differently: *"Use only the cases I paste below. Do not generate case names or citations from your training data. If no supplied case supports the argument, say so."* Specific context. Clear constraints. Explicit instructions about what not to do.

A 2022 study by Peng et al. (GitHub/Microsoft Research) found that software developers using GitHub Copilot completed a standard coding task 55.8% faster than those without it. But the gains weren't evenly spread. They were concentrated among developers who briefed the AI clearly — described the goal, specified the constraints, gave examples of what they wanted. Developers who just typed "write this function" got generic output that needed heavy reworking. The prompt quality mattered as much as the tool itself.

Two industries. Two sets of professionals. Same finding: **prompt quality has real consequences.** Same tool. Wildly different results.

---

## Try-It

Watch the recipe build, one piece at a time.

**Start with the weak prompt.** Open your AI tool (Codex or Claude) and run this exactly:

> `help me study for my quiz`

Read what comes back. It'll be generic — because it doesn't know what subject, what topics, what kind of help, or how much time you have. It did its best with nothing.

**Now build the strong version, one piece at a time.**

Watch what changes after each addition:

1. **Add Role:** *"You are a patient tutor who explains things with real examples."*
   → Run it. The tone shifts.

2. **Add Context:** *"I'm studying for a history quiz on the causes of World War I. I understand Nationalism but I'm shaky on Alliances and Imperialism."*
   → Run it. The content becomes specific.

3. **Add Task:** *"Explain Alliances and Imperialism in two paragraphs each, with one real historical example per paragraph."*
   → Run it. The output has shape.

4. **Add Format:** *"Keep each paragraph under 100 words. End with three practice questions, starting easy and getting harder. No bullet points."*
   → Run it. The output is usable.

**Compare your first run to your last run.** Same model. The only thing that changed was what you gave it.

**Now try your own.** Take one weak prompt you'd normally type — something vague you'd actually ask — rewrite it with the five-piece recipe, run both, and save the better version.

---

## Guided Lab: Build Your Study Prompt

You're going to build one strong prompt for something you're *actually studying right now*. By the end, you'll have something reusable — swap the topic each week and the prompt works again.

**Step 1 — Pick your subject and topic.**
Don't write "science." Write something specific: "cell division," "the French Revolution," "slope-intercept form," "photosynthesis and cellular respiration." The more specific, the better.

My topic: _______________

**Step 2 — Write the Role.**
> "You are a [tutor/teacher] who [how you want them to teach]."

Example: *"You are a patient math tutor who always starts with a real-world example before explaining the formula."*

My Role: _______________

**Step 3 — Write the Context.**
2–3 sentences. What's the topic? What do you already understand? What's still confusing?

Example: *"I'm studying slope-intercept form in Algebra. I understand what slope means but I keep mixing up where the y-intercept goes in the equation y = mx + b."*

> Tip: be specific enough that a tutor who knows nothing about your class could still help you.

My Context: _______________

**Step 4 — Write the Task.**
Exactly what you want: an explanation, a summary, a quiz, a comparison, worked examples.

Example: *"Explain slope-intercept form step by step, using a graph example and a real-life example. Then give me two practice problems."*

My Task: _______________

**Step 5 — Write the Format.**
How long? What style? What should it *not* do?

Example: *"Keep it under 200 words. No bullet points. End with two practice problems — one easy, one harder."*

My Format: _______________

**Step 6 — Add the review line.**
Before you run it, add this as your final line:

> *"Show me a first version for review before we go further."*

This is a habit. Any time the output is going somewhere — you're going to submit it, share it, print it — this line is your safety net. We'll talk more about why in Module 12.

**Step 7 — Run it. Then iterate.**
Read what you get. What was good? What was missing or off?

Add one more instruction and re-run. Examples:
- Output too long → add a word limit
- Too generic → add "use a real example, not a hypothetical"
- Missing a key point → add it to the Context
- Tone wrong → specify it in Format

Save your finished prompt. Replace [TOPIC] each week — the structure works for any subject.

**Success looks like:** you have a 5-element prompt you ran at least once and improved once. The final output is meaningfully better than "explain [topic]" would produce.

---

## Level up: the operating brief

Once you've used the recipe a few times, it becomes instinct — you'll stop thinking "did I hit all five pieces?" and just start writing clear prompts naturally.

When tasks get bigger, the pros use a slightly more formal version. Same idea, more precise:

```
Goal:          What are we trying to accomplish?
Context:       What should it understand about the situation?
Deliverables:  What exactly should it give me back?
Constraints:   What should it avoid, not change, or ask me about first?

— Module 10 adds:
Inputs:        What files, tools, or data should it use?
Verification:  What evidence will prove the work is correct?
```

The top four are what you're already doing — your Guided Lab prompt hits all of them. Inputs and Verification become important in Module 10, when you're giving AI agents multi-step tasks to run autonomously. They're about keeping the agent grounded and checkable. For now: notice you were already doing the core version.

> One sentence on a risk worth knowing: because prompting is powerful, people sometimes hide instructions inside content (a shared doc, a webpage) — trying to redirect the AI without you knowing. We'll cover this properly in Module 12.

---

## Share

Post your finished study prompt — not the AI's output, the *prompt itself*.

Include: your subject + one sentence on what you noticed between your first run and your final one.

---

## The one thing to remember
*Prompting is clear communication. Role + Context + Task + Format + Iterate beats a vague ask, every time.*

---

## Artifact
**A reusable prompt you'll actually use this week.** The one from the Guided Lab — saved somewhere you'll find it. Every time you swap the topic, you're reusing the thinking you did here.

Want a head start? The fill-in-the-blank template from the Concept section works for almost anything:

```
Create [output] for [audience].
The purpose is [goal].
Use the attached [source material] as the source of truth.
It should feel [three useful adjectives].
Include [requirements or constraints].
Show me a first version for review before publishing, sending, sharing, or changing access.
```

---

## Go Deeper →
*(Verify links before publishing — URL check needed.)*
- **Anthropic — "Prompt Engineering Overview"** Anthropic's own plain-English guide: clear instructions, examples, format, role, chain-of-thought. → https://docs.anthropic.com/en/docs/build-with-claude/prompt-engineering/overview
- **OpenAI — "Prompt Engineering Guide"** OpenAI's version of the same ideas — good for seeing that the recipe isn't Claude-specific. → https://platform.openai.com/docs/guides/prompt-engineering
- **Ethan Mollick — "A Guide to Prompting AI"** A Wharton professor's honest, practical take on what works and what doesn't. Updated as the landscape changes. → https://www.oneusefulthing.org/p/a-guide-to-prompting-ai-for-what
- **Peng et al. (2022) — "The Impact of AI on Developer Productivity"** The GitHub/Microsoft Research study behind the 55.8% stat — useful for anyone who wants to see the original data. → https://arxiv.org/abs/2302.06590
- **CSET — "The Surprising Power of Next-Word Prediction"** Why the model responds so strongly to framing — the mechanism behind why prompting works. → https://cset.georgetown.edu/article/the-surprising-power-of-next-word-prediction-large-language-models-explained-part-1/
- **Learn Prompting** Free, open-source, community-maintained guide to prompt techniques. Start with the Basics section. → https://learnprompting.org

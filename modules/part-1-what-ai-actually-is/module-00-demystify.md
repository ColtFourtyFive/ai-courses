# Module 00 · Start Here: Demystify
**Owner:** Ayan  ·  **Status:** Ready to review  ·  **Emotional target:** fear → "wait, I made that?"
**Research brief:** `research-briefs/module-00-research-brief.md`  ·  **Research notes:** `research-notes/module-00.md`

## Spec (from sources/Master-Build-Plan.md)
- **Covers:** no theory; a first real build in ~15–20 min by describing it in plain English; the reframe that the wall is smaller than it looks; a 20-second map of where the course goes.
- **Repurpose from:** *Beyond Code* "pick one stage and make a first version" hands-on pattern (format only).
- **Build new:** the exact 5-minute "unlock" build (jaw-dropping AND dead-simple); 3–4 teen-relevant build options; the opening framing.
- **Blocks:** Mission (guided) + minimal Concept.
- **Artifact:** a working thing, made day one.

### Owner notes (resolve before publishing)
- **Tool to name:** The builds below rely on AI tools that show interactive HTML in a live preview panel (Claude.ai's Artifacts panel is the primary example). Specify which tool(s) the course uses and include the exact UI instruction — e.g., *"In Claude.ai, interactive builds appear in a preview panel on the right side of the screen."*
- **Fallback:** If the tool gives code instead of a running preview, the module includes a fallback instruction — verify it matches the tool you're recommending.
- **Account creation:** Draft assumes a signed-in account. If learners create accounts in this session, add ~5 min to the estimate.
- **Sharing mechanic:** The artifact works best with a cohort share feed or screenshot submission. If the platform doesn't have this yet, the fallback is: *"Copy your build prompt + a description of what appeared into your notes."*

---

# Module 0 · Start Here: Demystify
Emotional target: fear → "wait, I made that?"   ·   Est. time: ~15–20 min

## Why this matters

Most people hear "AI" and think: *that's not for me.* Too technical. Too complicated. Something for people who already know how this stuff works.

This module exists to prove that was wrong — before you've learned a single thing about how AI works.

You're going to build something. Something interactive. Something that runs. In about fifteen minutes, by describing it in plain English.

The rest of the course explains the why and makes you better at this. Module 0 just proves you can start — right now, today.

## What you'll walk away with
- One working interactive build you made today, in a single session
- The feeling of describing something and watching it appear
- Your first steering move — changing a result by describing what you wanted differently

---

## Concept

One thing to know before you start.

**AI tools respond to plain-English descriptions. You describe what you want. A result appears.**

No code. No special commands. No background in technology. Whatever you can describe clearly, you can ask for. The interface is a text box. You type. Things happen.

That's it. Let's go.

---

## Mission

**Pick one option. Describe it. Watch what comes back.**

Three options below — each one is for a different type of person. Read them and pick the one that's most you. Then follow the steps.

---

### Option A — Interactive quiz game on your topic
*Best for: anyone with a topic they actually know — a game, sport, show, band, subject, anything*

**What you'll get:** Not a list of questions to read. A game you click through. Multiple choice buttons. A score counter. A result screen at the end. A piece of software built around something you know well.

**Step 1 — Paste this prompt into your AI assistant. Fill in the brackets.**

```
Build me an interactive quiz game I can play in the browser.

Topic: [YOUR TOPIC — be specific. "Premier League 2024-25 season" beats "soccer."
        "AP US History, unit 3 — the Civil War" beats "history."]

Requirements:
- 8 questions, multiple choice with 4 options each
- Show whether I got each one right or wrong immediately after I click
- If I got it wrong, show the correct answer and a one-sentence explanation
- Running score counter visible throughout
- Final results screen with my score out of 8 and a message that matches how I did

Build it as interactive HTML with real clickable buttons — I want to actually play it,
not just read it.
```

**Step 2 — Once it loads, actually play it.** Click through all 8 questions. Notice: the buttons work. The score updates. You didn't write a line of code. You described what you wanted.

**Step 3 — Notice what's surprising.** It knew enough about your topic to write questions — and to make the wrong answers genuinely tricky if you don't really know the subject. That's the thing worth sitting with for a second.

---

### Option B — Study tool built from your class notes
*Best for: anyone with an upcoming test or class they actually need to study*

**What you'll get:** Your real class notes — the ones you took — turned into a working flashcard app. Cards you can flip. Buttons to mark what you know and what you need to review. A running count. An end-of-session list of everything to go back to.

**Step 1 — Paste this prompt. Fill in your actual notes.**

```
I need a study tool built from my class notes. Here they are:

[PASTE YOUR NOTES HERE — bullet points, full sentences, messy shorthand, whatever you have.
 Don't clean them up. Paste them as-is.]

Build me an interactive HTML flashcard app using these notes:
- One card at a time — show the term or concept on the front
- I click to flip it and see the definition, explanation, or answer on the back
- Two buttons after I flip: "Got it ✓" and "Review again ↺"
- Running progress tracker: how many I've gotten vs. how many are still in the review pile
- At the end, show me a list of everything still in "review again" — those are what I study next

Make it work with real clickable buttons and actual flip animations if possible.
```

**Step 2 — Use it for a few minutes.** Click through five or ten cards. Mark some as "got it," mark some as "review again." Watch the tracker update.

**Step 3 — Notice what's surprising.** This used your specific notes from your specific class. It's not a generic quiz — it's a study tool built around what you actually need to know, for the test you actually have.

*Don't have notes yet? Use Option A or C and come back to this one before your next exam.*

---

### Option C — A tracker or tool for something you actually care about
*Best for: anyone into sports, fitness, gaming, reading, music, creative projects — anything with data worth tracking*

**What you'll get:** A small, working app for something specific to your life. Something you'd normally download an app for — except you're about to describe it and get it back in two minutes.

**Pick your version:**
- Workout log — add exercises, sets, reps, weight; see your session history
- Game stats — log wins, losses, kills, scores; see your win rate over time
- Book list — log what you've read, give it a rating, search by rating
- Habit tracker — check off daily habits; see your current streak
- Anything else — if you can describe what you want to track and what you want to see, it'll work

**Step 1 — Paste this prompt. Fill in your version.**

```
Build me a [DESCRIBE YOUR TRACKER — e.g., "workout log" / "game stats tracker" / "reading list"].

What I'm tracking: [describe the specific thing — e.g., "each exercise in a gym session: 
                    exercise name, sets, reps, and weight"]

What I want to see: [e.g., "a table of my entries, a total volume for the session, 
                     and a history of past sessions"]

How I add entries: [e.g., "a simple form at the top with input fields and an 'Add' button"]

Here's one example entry so you understand the format:
[give one realistic example — e.g., "Bench press — 3 sets, 8 reps, 135 lbs"]

Build it as an interactive HTML page with working buttons and inputs. 
Keep it clean and simple, but make it actually functional.
```

**Step 2 — Add some real data.** Don't just look at the empty template. Add three or four real entries — actual workouts, actual games, actual books. Watch the table or list populate with your real data.

**Step 3 — Notice what's surprising.** You described a piece of software. Software appeared. It does the thing you described. You've been using apps your whole life — you just built one.

---

## Now steer it

Whatever you got back from any of the three options: don't start over. Read it. Find one thing that's not quite right or one thing you want changed. Then tell it exactly what you want:

*"The score counter isn't resetting between games — fix that."*
*"The wrong-answer explanations are too short — make them more detailed."*
*"Change the color scheme to something darker."*
*"Add a timer that counts down 10 seconds per question."*
*"The form inputs are too small on mobile — make them bigger."*

One message. One specific change. Watch it update.

This is the skill — not the first prompt, but everything after it. Every build you do for the rest of this course follows exactly this pattern: a first version, then steering until it's right. You just learned the whole loop.

---

## A quick note if you got code instead of a running app

Some AI tools show interactive builds in a live preview panel — click "run" or look for a preview button. If yours gave you HTML code instead of a running page, copy the code, paste it into a new file, save it as `build.html`, and open that file in any web browser. It'll run the same way.

---

## Where this goes

You just did the whole thing: described something, got it back, changed it until it was right. That loop — describe, get, steer — is the foundation of everything that follows in this course.

Module 1 explains *why* it works at all. Modules 2–5 make you dramatically better at the describing part. Modules 6–10 hand you enough control to build things that run on their own, without you watching — tools that do work while you're doing something else.

One more thing worth saying: what you just did isn't a school exercise. Teams at real companies are doing exactly this right now — describing the internal tools they need and getting them back in minutes, without writing code or waiting for an engineer. Most people haven't figured out how to do this well yet. You just did it, in your first session.

---

## The one thing to remember
*You describe it. It appears. The wall was smaller than it looked.*

---

## Artifact

**Your working build + one sentence.**

Save or screenshot your working build. Then write one sentence:

> *"I described [what you asked for] and got back [what appeared]. The part that surprised me was [one specific thing]."*

**A completed example:**
> *"I described a flashcard tool built from my AP Bio notes on cell division and got back a working app where I could flip cards and mark them. The part that surprised me was that it organized the terms into a logical order — it grouped the stages of mitosis together instead of leaving them scattered like my original notes."*

Post your sentence with a screenshot or copy of your build. It doesn't have to be perfect. It just has to be yours.

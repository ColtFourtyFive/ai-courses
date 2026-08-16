# Research Notes — Module 2: LLM vs Chatbot vs Agent

## Concept check

**The three-layer ladder in Curriculum.md is accurate and current as of Aug 2026. Keep it as the canonical spine.** Notes on each layer below, plus what needs small updates.

- **LLM / brain layer.** Curriculum.md currently names "GPT-5, Claude Opus, Gemini" as model examples. Verify status:
  - Claude family (Aug 2026): **Opus, Sonnet, Haiku** are still the three live tiers (this matches what this very agent's own tooling exposes — a "Sonnet 5" model identity, with "opus"/"haiku"/"fable" as sibling options). Multiple 2026 blog/review sites also describe a lineup of Opus / Sonnet / Haiku (with version-number churn — treat exact version numbers like "4.8" or "5" as **volatile and not worth teaching**; teach the tier names Opus/Sonnet/Haiku, not the version number).
  - OpenAI: sources describe **GPT-5.6** ("Sol" being the top tier) as the current flagship generation as of July 2026, evolved from GPT-5. "GPT-5" as a family name is still reasonable to teach as the generation name; exact dot-version will be stale within months.
  - Google: **Gemini 3** is the current frontier family (3.1 Pro flagship, plus Flash variants) as of Aug 2026.
  - **Recommendation for the module text:** don't hard-code a specific version number (e.g. "GPT-5.6" or "Claude Opus 4.8") since it will look dated within a quarter. Say **"GPT, Claude, Gemini"** (family names) and note in a caption/footnote that exact version numbers change often — this also matches the de-vendor guardrail (concept first, vendor names as illustration only).
  - Confidence: high on "Opus/Sonnet/Haiku" and "Gemini 3" and "GPT-5.x" existing as families; medium on exact current dot-version (fast-moving, low-quality SEO sites dominate search results — see Couldn't Verify).

- **Chatbot / app layer.** Curriculum.md names ChatGPT, Claude.ai, Gemini (the apps) — **still accurate**. Confirmed via Anthropic's own Help Center (support.claude.com) that **web search and memory in Claude.ai are explicitly app/product features**, gated by plan tier (Pro/Max/Team) and by client (web/desktop/mobile) — not something inherent to the model. This directly supports the module's core claim: *"browsing, memory, and tools are features of the app, not the brain."* Same pattern confirmed for ChatGPT: memory is opt-in/off-by-default in Settings → Personalization, a product-level toggle, not a model property.
  - "ChatGPT" ≠ "GPT" claim: **confirmed accurate and still the standard way OpenAI/community explainers describe it** — ChatGPT is "the ready-to-use product," the API/model is "the raw model... the engine under the hood." Good teen-legible phrasing to borrow.

- **Agent layer.** Claude Code and Codex are **both still real, current, widely-used coding agents in Aug 2026** — good to keep as the two named examples (matches de-vendor: naming both, not favoring one). Computer-use agents also confirmed as a current real category (Anthropic's Computer Use / "Claude Computer Use", OpenAI's Codex Background Computer Use as of April 2026). Safe to keep "computer-use agents that click around a screen" as the third example.

- **Harness / scaffold terminology.** **Confirmed this is exactly the term the field uses right now**, including used natively by Anthropic itself:
  - Anthropic's own engineering blog: *"Effective harnesses for long-running agents"* (anthropic.com/engineering/effective-harnesses-for-long-running-agents, published Nov 26, 2025) — Anthropic uses "harness" to describe the wrapper (tools, loop, environment setup) around the Claude Agent SDK.
  - Hugging Face's 2026 agent glossary formalizes: **Agent = Model + Harness**, where harness = "the execution layer... calls the model, handles its tool calls, decides when to stop," and separately defines "scaffold/scaffolding" as the behavior-shaping layer (system prompt, tool descriptions, memory). Curriculum.md currently treats "harness" and "scaffold" as interchangeable ("harness (or scaffold)") — technically some 2026 sources draw a finer distinction (scaffold = behavior-shaping, harness = execution loop) but for a beginner audience, **treating them as synonyms is a reasonable simplification and matches how most casual/press usage still treats them.** Flagging the finer distinction under Open Questions in case the owner wants precision.
  - Verdict: **no change needed** to the harness framing in Curriculum.md — it's accurate and current terminology, not at risk of going stale.

- **Agent definition ("brain + goal + tools + a loop") — strongly validated.** This phrasing is now essentially industry consensus. Simon Willison (widely-read, credible independent AI engineer) proposed and got broad adoption for: **"An LLM agent runs tools in a loop to achieve a goal."** (Sept 18, 2025 post, after crowdsourcing 211 competing definitions). This is close to a word-for-word match with the module's own line — good confirmation the module isn't inventing/oversimplifying, it's teaching the real current definition.

## Best analogy / demo

**The brief's demo — "web access off vs. on, same brain, different powers" — is buildable exactly as specified. Concrete recommended version:**

- **Setup:** one assistant/app that has a web-search toggle in the same conversation UI (Claude.ai and ChatGPT both support this — confirmed, see Concept check above).
- **Question to ask (needs today's internet, not training data):** pick something dated/volatile at the time of teaching, e.g.:
  - A live sports score: *"What was the score of [most recent big game], and who won?"*
  - A live price: *"What's [a specific well-known stock or crypto ticker] trading at right now?"*
  - A very recent news event: *"What happened in [topic] this week?"*
  - Recommend the module **not hard-code a specific example** (it'll be stale by the time a learner runs it) — instead give the *pattern* ("ask something only today's internet would know: a live score, a live price, this week's news") and let the learner pick their own live example. This also makes it more concrete/personal for them.
- **Steps:**
  1. Turn web search **off**. Ask the question. Watch it either decline, hedge ("I don't have real-time data..."), or guess from training data (possibly wrong/outdated).
  2. Turn web search **on**. Ask the *same* question again in the same chat. Watch it search and return a current, cited answer.
- **The teaching moment:** same model both times — nothing about "the brain" changed. What changed is a *tool the app gave it access to*. This is the app/harness layer made visible in real time, in under 2 minutes.
- Confirmed both major consumer apps support toggling this live: Claude.ai has a web search toggle available across tiers; ChatGPT has browsing controllable via settings. Either works for the demo — keep de-vendored by describing generically ("in your assistant of choice, look for a web search toggle").

## Teen-relevant example(s)

Brief's suggested task — "turn my messy notes into a finished study guide + quiz" — fleshed out concretely:

- **Chatbot version (brain + conversation only):**
  1. Learner pastes messy class notes into the chat, asks for a study guide.
  2. Chatbot replies with a draft study guide in the chat window.
  3. Learner has to: copy it out, format it themselves, then separately ask for quiz questions, copy those out too, then manually assemble both into one usable document/file.
  4. **Key point to teach:** the chatbot did the *thinking*, but the learner did all the *follow-through* — assembling, saving, formatting, combining multiple replies into one finished thing.

- **Agent version (brain + goal + tools + loop):**
  1. Learner gives a goal: "turn these notes into a finished study guide with a quiz at the end, saved as one document."
  2. An agent (e.g., a Claude Code–like tool operating on files, or any agentic app with file-write access) would: read the notes file, draft the guide, draft the quiz, combine them, save the finished file — checking its own output and iterating — without the learner manually stitching pieces together.
  3. **Key point to teach:** the agent doesn't just answer — it takes the actions needed to *produce the finished artifact* and hands back something already done, closer to "done" than "a reply to work from."
  4. Good contrast line for the module (matches Osman's material, reworded teen-scale): *chatbot = you ask, it replies, you do the rest; agent = you set the goal, it does the work and hands you the finished thing.*

- Note: this is a good place to be honest that **most teens' daily tools are chatbots, not agents** — coding agents like Claude Code are the accessible real example of the agent layer for a curious teen, but this specific "study guide" agent workflow is illustrative/conceptual rather than something with one universal one-click teen tool today. Frame it as "this is what an agent *would* do," not "download this specific app."

## Real business example(s)

**Osman's "chatbot vs. working environment" material (Source-Material-Library.md, Module 2 entry) — verified present and ready to adapt, use as-is per the library's own adapt note:**

> "A traditional chatbot answers a question. A working AI environment can understand your team's context, reason through complex work, take action across tools, and help build repeatable ways of working."
> "ChatGPT Work and Codex are environments for doing work with AI, not just asking it questions. You set a goal, provide context, review the approach, steer the work, and end with a useful artifact… the conversation is no longer the final product."

- **Adapt guidance (already given in the library, confirmed still correct):** use this for the chatbot→agent rung; keep the real "team report" framing intact per the source-library adapt note ("keep the real 'team report' example too — it shows how a workplace actually uses this").
- **Concrete framing to use in the module:** "A real team doesn't just ask a chatbot 'summarize this data' — they set up an agent-style workflow that goes and pulls the data, drafts the report, and comes back with a finished document to review, not just a chat reply to copy out." This mirrors the teen example structurally (chatbot = reply you finish yourself; agent = goal you hand off and get a finished artifact back) — good parallel structure for the module to make explicit.
- This is directly attributable to Osman's *Work With AI* workshop material — per Source-Material-Library.md instructions, keep it "professional/Codex-flavored" and de-vendor only per the standard guardrail (name Codex as *an* example, don't over-index).

## Interactive block

Two components, per spec:

**(a) Tool-on/off experiment (the Try-It):**
- Materials: any consumer chatbot with a visible web-search toggle (Claude.ai, ChatGPT, Gemini app all qualify — confirmed above).
- Task: ask the same "only-today's-internet-would-know" question with the toggle off, then on, in the same conversation.
- Success criteria: learner can articulate *in their own words* that (1) the same model answered both times, (2) what changed was a tool/permission the app gave it, and (3) name that layer as "the app/harness," not "the brain."
- Suggested prompt for the learner to fill in afterward: *"When I turned web search off, it [said / guessed / got it wrong]. When I turned it on, it [got today's real answer / cited a source]. What changed wasn't the brain — it was ___."*

**(b) Artifact — labeled diagram of a real assistant (model vs. bolted-on):**
Concrete content spec for what the diagram should contain (for whoever builds/draws it):
- **Center/base box:** "The model" (the brain) — label it with a generic name like "GPT / Claude / Gemini" — plain text in, plain text out, nothing else.
- **Surrounding boxes, each connected by an arrow labeled "added by the app, not the model":**
  - "Memory" — remembers past chats/preferences
  - "Web search" — can look up current info
  - "File upload / file access" — can read documents, images, spreadsheets
  - "Tools / integrations" — connectors to other apps (Drive, Slack, etc. — matches Claude.ai's confirmed connector features)
  - (Optional, for agent-tier stretch) "The loop" — a box specifically showing "plan → act → check result → decide next step," to visually distinguish chatbot-tier (no loop, one reply) from agent-tier (loop, multiple actions before returning).
- **Visual idea:** model as a plain box in the middle; app features as add-on modules bolted around it with dashed-line arrows (to visually suggest "detachable/optional," reinforcing that these aren't intrinsic to the brain). A simple three-column version (LLM | Chatbot | Agent) each showing what's newly added at that tier would also satisfy the spec and ties directly back to the ladder structure.
- Learner should be able to point at *any one box* and say whether it's "brain" or "body" — that's the artifact's real success criterion, not visual polish.

## Open questions / needs owner's judgment

- **How much to formalize "harness" vs. "scaffold" as distinct terms.** 2026 field usage is trending toward a finer distinction (scaffold = behavior-shaping layer i.e. system prompt/tool descriptions/memory; harness = the execution loop that calls the model and handles tool calls) per Hugging Face's 2026 agent glossary and Anthropic's own harness-focused engineering posts. Curriculum.md currently uses them as synonyms ("harness (or scaffold)"). **Recommendation: keep them as synonyms for this module** — the brain/body metaphor alone carries the weight a beginner needs, and introducing a second layer of jargon (scaffold ≠ harness) risks the "textbook wall" AGENTS.md warns against. Flagging for owner sign-off since the field is trending toward a real distinction that a more advanced "Go Deeper" reader might notice.
- **Is the brain/body metaphor sufficient alone, or does "harness" need its own mini-definition beat?** Current Curriculum.md draft does introduce "harness" as a vocabulary payoff ("one more term that makes you sound sharp") after the brain/body idea is already landed — this sequencing (concept first, then the label) matches AGENTS.md's "analogy before definition" rule well. Recommend keeping that order in the module.
- **Version-number specificity for model names.** Given how fast model version numbers are turning over in 2026 (Claude, GPT, and Gemini all had multiple point releases within months), recommend the module text use family names only (Claude/GPT/Gemini) and avoid printing a specific dot-version anywhere in learner-facing copy, to avoid the module reading as dated within a semester. This is a judgment call for the writer, not just research — flagging explicitly.
- **Teen agent example concreteness.** The "study guide + quiz" agent scenario (per brief) is conceptually solid but there isn't one single, obviously teen-accessible "one-click" agent product to point to for it today the way Claude Code is a real accessible thing for a curious teen to try in the coding domain. Recommend the writer frame the study-guide scenario as an illustrative "here's what an agent *would* do" rather than "go install this," and lean on Claude Code as the thing a teen could actually try hands-on if the module wants a genuinely try-able agent example.

## Go Deeper references

All verified live and on-topic as of this research pass:

1. **Anthropic — "Building Effective Agents"** — https://www.anthropic.com/research/building-effective-agents — Anthropic's own foundational explainer distinguishing workflows (predefined code paths) from agents (LLM dynamically directs its own process/tool use). Directly relevant to the agent definition.
2. **Anthropic — "Effective harnesses for long-running agents"** — https://www.anthropic.com/engineering/effective-harnesses-for-long-running-agents — Anthropic's own engineering blog using "harness" natively (published Nov 26, 2025), confirms the term is Anthropic's own current vocabulary, not just community slang.
3. **Simon Willison — "I think 'agent' may finally have a widely enough agreed upon definition to be useful jargon now"** — https://simonwillison.net/2025/Sep/18/agents/ — respected independent AI engineer/commentator; source of "An LLM agent runs tools in a loop to achieve a goal," near-identical to this course's canonical agent framing. Good "the pros use this exact definition" link.
4. **Hugging Face — "Harness, Scaffold, and the AI Agent Terms Worth Getting Right"** (May 2026) — https://huggingface.co/blog/agent-glossary — current (2026), credible (Hugging Face), directly defines model/scaffold/harness/agent as distinct-but-related terms; good deeper-dive link for a learner who wants the more precise version of the brain/body distinction.
5. **Claude Help Center — "Use Claude's chat search and memory to build on previous context"** — https://support.claude.com/en/articles/11817273-use-claude-s-chat-search-and-memory-to-build-on-previous-context — official confirmation, in plain support-doc language, that memory and search are app/plan-tier features layered onto Claude, not the model itself. Useful as a "see, it's literally in the product docs" citation for the module's core claim.

## Couldn't verify

- **Exact current model version numbers** (e.g., "Claude Opus 4.8," "GPT-5.6 Sol," "Gemini 3.1 Pro") — search results returning these are dominated by fast-turnaround SEO/content-mill sites (e.g. Coursiv, Claude Market, tech-insider.org, SecondTalent, tygartmedia, usecarly.com, explainx.ai, n1n.ai, mmahesh09.github.io) whose reliability I can't fully vouch for; I could not independently cross-check against each vendor's own official model page in this pass. The *pattern* (families = Claude Opus/Sonnet/Haiku, GPT-5.x, Gemini 3.x; frequent point-releases) is corroborated across multiple independent-looking sources including some outlets I trust more (TechCrunch, 9to5Google, Wikipedia, openai.com's own index pages), so I'm confident in the shape of the landscape, just not in pinning an exact version string into learner-facing copy. **Recommendation carried into Concept check and Open Questions above: don't hardcode a specific dot-version.**
- **Whether "Claude Fable" is a public, named consumer-facing model tier** vs. an internal/limited designation — one search result surfaced "Claude Fable 5" as a top-tier model name, and separately this very agent session's own tooling exposes "fable" as a selectable model option alongside sonnet/opus/haiku — which is suggestive corroboration, but I did not find an independent, citable public Anthropic announcement page naming a "Fable" tier during this research pass. **Do not put "Fable" in learner-facing copy without owner confirmation** — stick to Opus/Sonnet/Haiku, which are solidly confirmed.
- **A single, concrete, teen-usable one-click "agent" product for the study-guide-and-quiz task** — I could not identify one specific, widely available, teen-friendly agent app that performs this exact "notes → finished study guide + quiz file" workflow end-to-end today. The scenario is conceptually accurate and worth teaching, but should be framed as illustrative rather than "here's the app, go try it" unless the owner knows of a specific tool to name.

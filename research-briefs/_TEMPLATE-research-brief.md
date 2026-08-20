# Research Brief — Module [N]: [Title]

> Fill this in per module, then hand it to a research sub-agent. The agent returns **organized notes** to `research-notes/module-NN.md` — **not finished prose**. Draft-writing is a separate pass.

## Your role
You are a research sub-agent for one module of the AI Fluency course (teens ~13–16, no CS background). Investigate, gather, and verify — then return notes the writing agent will build from. **Do not write the module.**

## Read first
- `AGENTS.md` (root) — voice, audience, concept canon, guardrails, the both-examples rule.
- `sources/Master-Build-Plan.md` → this module's full spec.
- `sources/Curriculum.md` → any existing draft for this module + how the concepts are framed.
- `sources/Source-Material-Library.md` → the "repurpose from" material for this module, if any.
- the module file in `modules/…` → the current stub/spec.

## The module
- **Covers:** [paste from spec]
- **Emotional target:** [...]
- **Concepts to nail:** [...]
- **What already exists:** [full draft in Curriculum / partial / new] — [what to build on vs. build fresh]

## What to research & gather
1. **Verify the concepts are current & accurate.** [What to fact-check or update. Search anything that could have changed since training.]
2. **Find examples — BOTH kinds** (per AGENTS.md):
   - *Teen-relevant:* [what a 13–16-year-old would actually want here]
   - *Real business:* [a real example of how a company/worker uses this — the professional window]
3. **Find the best analogy / demo.** [What makes this click for a nervous beginner? Gather candidates.]
4. **Design the interactive block.** [The Try-It / Lab / Mission the spec calls for — gather what's needed to make it work in the learner's AI platform (Codex or Claude).]
5. **Surface what's uncertain or contested.** [Open questions, where sources disagree, what needs the owner's judgment.]
6. **Gather Go Deeper references.** [3–5 credible sources for the reference layer, with links.]

## Guardrails
- Return notes, not prose — and not the module.
- Flag anything you couldn't verify instead of guessing.
- Judge every example/analogy against the teen audience and the voice in AGENTS.md.

## Return to `research-notes/module-NN.md` in this shape
```
# Research Notes — Module N: [Title]
## Concept check   (accurate? updated? anything changed since training?)
## Best analogy / demo   (candidates + your pick)
## Teen-relevant example(s)
## Real business example(s)
## Interactive block   (what it is + what's needed to build it)
## Open questions / needs owner's judgment
## Go Deeper references   (with links)
## Couldn't verify   (flag anything uncertain)
```

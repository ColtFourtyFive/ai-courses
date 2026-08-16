# AI Fluency Course

A course that takes teens from "AI scares/confuses me" to "I understand it, I use it well, and I can build with it." Built by Ayan and Osman against five shared source-of-truth docs.

## Repo layout
```
AGENTS.md                     # agent brief — every agent auto-reads this (voice, canon, output shape, guardrails)
sources/                      # the other 4 source-of-truth docs (STABLE — change via PR only)
  Curriculum.md
  Format-and-Delivery.md
  Master-Build-Plan.md
  Source-Material-Library.md
modules/                      # ONE FILE PER MODULE (spec up top, draft below) — the deliverables
  part-1-what-ai-actually-is/   (00–04)
  part-2-using-ai-well/         (05–08)
  part-3-building/              (09–11)
  part-4-doing-it-right/        (12–13)
  capstone/
research-briefs/              # _TEMPLATE + one brief per module (01/02 pre-filled) — fill before researching
research-notes/               # research sub-agents drop notes here, one file per module
```

## Ownership
- **Ayan:** modules 00, 01, 02, 03, 04, 05, 13
- **Osman:** modules 06, 07, 08, 09, 10, 11, 12, capstone
See `.github/CODEOWNERS` (auto-requests the right reviewer on every PR).

## How we build each module — three passes
1. **Research** — fill a brief (`research-briefs/`), hand to a sub-agent → notes in `research-notes/`. Parallelize across modules (2–3 at a time); never across steps within a module.
2. **Draft** — a writing agent takes the module spec + its research notes + `AGENTS.md` → writes into the module file.
3. **Review** — the owner is the voice/taste filter before "ready to review."

## Build order (Ayan)
Module **01 → 02 → 00 → 05 → 03 → 04 → 13**.
## Build order (Osman)
Module **08 → 09 → 07 → 10 → 06 → 12 → 11 → capstone**.

## Start here
Read `AGENTS.md`, then `CONTRIBUTING.md` for the branching + clean-merge rules, then open a pre-filled brief (`research-briefs/module-01-…`) and launch the first research sub-agent.

# Contributing — branching & clean-merge rules

The repo is built so Ayan and Osman can work in parallel and **never hit a merge conflict**. The rules exist to keep it that way.

## The one rule that prevents conflicts
**One module = one file = one owner.** You only ever edit module files you own (see ownership in `README.md` / `.github/CODEOWNERS`). Since Ayan's modules and Osman's modules are different files, your branches never touch the same lines.

## Branching model
- `main` is always stable and mergeable.
- Work on short-lived branches off `main`, named by owner + module:
  - `ayan/module-01`, `ayan/module-02`, …
  - `osman/module-08`, `osman/module-09`, …
- Open a PR into `main` when a module hits *ready-to-review*. CODEOWNERS auto-requests the other person as reviewer.
- Keep branches short-lived: pull `main` before starting, and merge/rebase `main` in if your branch lives more than a day or two.

## What NOT to touch on a feature branch (the only real conflict risk)
- **`sources/` is stable and shared.** Do not edit the Curriculum, Format & Delivery, Master Build Plan, Source Material Library, or `AGENTS.md` inside a module branch.
- If a source genuinely needs to change, open a **separate, dedicated PR** that only touches `sources/` (or `AGENTS.md`). Both owners review it (CODEOWNERS enforces), it merges to `main`, then everyone pulls before continuing. This keeps shared docs from being edited in two branches at once.

## Keep the skeleton identical
Every module file uses the same shape: spec block at top, `--- DRAFT BELOW ---`, then the content. Don't rename sections or restructure the skeleton — consistent structure keeps reviews and merges predictable.

## Research notes
Each module's research notes are their own file in `research-notes/` (e.g. `module-08.md`), so parallel research never collides either.

## PR checklist (per module)
- [ ] Only the module file(s) you own changed (plus its research brief/notes).
- [ ] Matches `AGENTS.md` voice, canon, and output shape.
- [ ] Uses both a teen example and a real-business example where relevant.
- [ ] Hits *ready-to-review*: core content drafted + one interactive block + artifact defined.
- [ ] No edits to `sources/` (those go in their own PR).

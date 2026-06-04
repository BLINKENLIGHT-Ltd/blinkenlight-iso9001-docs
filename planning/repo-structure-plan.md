# Repository structure: meta + QMS submodule

Captures the agreed restructure of the working tree so that the QMS
sits in its own git repository, added back to the parent as a
submodule. Approved 2026-06-03 by Patrick.

## Motivation

- The auditor handover should be the QMS only; meta-information
  (CLAUDE.md instructions, planning notes, research, GAPS, the
  adversarial-review tracker) must not be exposed.
- The QMS git history should start with a single clean, signed v1.0
  commit and accumulate audit-appropriate signed commits thereafter,
  rather than carry the messy drafting history.
- Meta files (planning, README, audit-pack scripts) should continue to
  be committed freely with the usual narrative style.
- Top-level `git status` should still show when the QMS has
  uncommitted changes or has moved to a new commit (the value over a
  fully separate repo).

## Target structure

```
iso9001/                            (parent repo — meta)
├── .git/
├── .gitignore                      (now includes qms/ — submodule
│                                   pointer is tracked via .gitmodules)
├── .gitmodules                     (records the qms submodule)
├── CLAUDE.md
├── README.md
├── planning/
│   ├── GAPS.md
│   ├── PLAN.md
│   ├── adversarial-review-findings.md
│   ├── aalto-engagement-walkthrough.md
│   ├── repo-structure-plan.md      (this file)
│   ├── equipment-inventory.md
│   ├── equipment-evidence/
│   └── research/
├── audit-pack/                     (rendered PDFs, when produced)
└── qms/                            (submodule — its own .git)
    ├── .git
    ├── (the QMS contents)
    └── …
```

## QMS repo

- Name: `blinkenlight-qms` (private GitHub repository, to be created
  by Patrick before the surgery).
- Owner: Patrick Coleman.
- Branch protection on `main` requiring signed commits.
- First commit: signed by Patrick, titled `QMS v1.0 initial issue`,
  containing the QMS files in their state at the time of the surgery.
  Commit message body lists the document set (QM-01..QP-17, MDL-01,
  REG-01..04, templates) and confirms approval.
- Subsequent commits follow QP-01 §6 message format: `<DOC-ID>
  v<version>, <short description>` — no Claude attribution
  (per CLAUDE.md "Commit messages" section).

## Surgery procedure

Pre-conditions:

- Patrick has created the empty private GitHub repository
  `blinkenlight-qms`.
- All pre-v1.0 sweep edits are complete and the QMS is in the state
  intended for v1.0 (sweep completed 2026-06-03 per GAPS).
- Working tree under `iso9001/qms/` reflects the desired v1.0 state.

Steps (each git command requires explicit Patrick approval per
CLAUDE.md):

1. Initialise `qms/` as its own git repository:
   - `cd /home/blinken/Documents/blinkenlight/iso9001/qms`
   - `git init`
   - `git config commit.gpgsign true` (or SSH signing — matching the
     parent repo's signing configuration)
   - `git remote add origin git@github.com:blinken/blinkenlight-qms.git`
2. Stage and commit the QMS as v1.0:
   - `git add .`
   - `git commit -S -m "QMS v1.0 initial issue" -m "<body>"`
     where `<body>` lists the document set and references QP-01.
3. Push to GitHub:
   - `git push -u origin main`
4. Configure branch protection on `main` requiring signed commits
   (via the GitHub web UI — Patrick to do).
5. Untrack `qms/` in the parent and clear it for the submodule:
   - `cd /home/blinken/Documents/blinkenlight/iso9001`
   - `git rm --cached -r qms`
   - Add `qms/` to `.gitignore` is NOT needed — the submodule pointer
     is what the parent tracks. Remove any `qms/` entry that may have
     been added in earlier discussion.
   - `rm -rf qms`     (clears the working directory; the submodule
     add re-populates it)
6. Add the QMS as a submodule:
   - `git submodule add git@github.com:blinken/blinkenlight-qms.git qms`
7. Commit the submodule reference in the parent:
   - `git add .gitmodules qms`
   - `git commit -m "convert qms/ to submodule pointing at blinkenlight-qms"`
8. Verify:
   - `git status` at parent: clean.
   - `git status -C qms` (or `cd qms && git status`): clean, on `main`.
   - `cat .gitmodules`: records the submodule URL.

## After the surgery: working pattern

- **QMS edits**: `cd qms`, ensure on `main` (`git checkout main`),
  make changes, `git add`, `git commit -S` with QP-01 §6 message,
  `git push`. Then back at parent: `git add qms`, `git commit
  -m "bump qms submodule to <short description>"` — this updates the
  parent's pointer to the new QMS commit.
- **Meta edits**: at parent, normal narrative commits.
- **Clone**: `git clone --recurse-submodules <parent>`; or
  `git submodule update --init` after a plain clone.
- **Pull**: `git pull --recurse-submodules` at parent picks up both.

## Risks and mitigations

- **Detached HEAD inside qms after submodule update.** Mitigation:
  always `cd qms && git checkout main` before working.
- **Parent points at QMS commit that doesn't exist (after a forced
  rewrite in the QMS repo).** Mitigation: never force-push the QMS
  `main`; if a rewrite is genuinely needed, re-push the parent's
  submodule pointer in the same change.
- **Forgetting to commit the parent's submodule bump.** Mitigation:
  `git status` at parent shows `qms (new commits)` until the bump is
  committed.

## Out of scope of this restructure

- Rewriting the parent repo's prior history (the meta repo's history
  before this change still contains old `qms/` blobs; it is not
  exposed to the auditor and is left as-is).
- Building the Audit Pack render script (deferred; tracker A3).
- Migrating planning material into the QMS (planning is meta by
  design and stays in the parent).

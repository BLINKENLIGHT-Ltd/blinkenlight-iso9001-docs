# BLINKENLIGHT ISO 9001 — repo guidance for future Claude Code sessions

This repository is the working area for BLINKENLIGHT Ltd's ISO 9001:2015
(International Organisation for Standardisation Quality Management Systems) certification journey.

The full Quality Management System (QMS) — Quality Manual, procedures,
records, and templates — will live in this repository over time, version-
controlled in Git, rendered through GitHub's private-repo web UI for auditor
and reviewer access. Git history itself satisfies clause 7.5 (Control of
Documented Information) of ISO 9001:2015.

## Goal

UKAS-accredited (United Kingdom Accreditation Service) ISO 9001:2015
certification of BLINKENLIGHT Ltd. This is the priority-1 credibility gate
identified in the wider BLINKENLIGHT repositioning work: it directly
addresses the conversion problem where established certified OEM (Original
Equipment Manufacturer) buyers were lost at the second meeting on
perceived size and the absence of UKAS-accredited ISO 9001.

Non-UKAS "mill" certificates are explicitly out of scope. They fail with
the buyers this certification is intended to convert.

## Standing principles (hard guardrails)

1. **Evidence-driven, not boilerplate.** The QMS must be built around real
   engineering records from real project work, not retrofitted templates.
   Auditors and AI-aware regulators are actively looking for AI-generated
   boilerplate that does not reflect actual practice; producing it fails
   Stage 2.
2. **No fabrication.** Never invent equipment, suppliers, procedures,
   calibration history, supplier-evaluation records, or audit history.
   Where real input is needed, insert `TODO(patrick)` placeholders and
   list every one in `GAPS.md`.
3. **UKAS-accredited only.** All certification body shortlisting must
   verify accreditation directly against ukas.com, not the body's own
   marketing.
4. **British English** throughout. Expand acronyms on first use per file.
5. **AI-maintained QMS, but human-approved.** Claude Code drafts and edits;
   Patrick reviews and approves each commit. The git commit (signed) is
   the approval record for that document version.
6. **Sole operator.** BLINKENLIGHT Ltd is the certified entity, not
   Patrick. Individuals cannot be ISO 9001 certified.

## Source-of-truth context (read-only, outside this repo)

These files are authoritative. Read them when relevant; never edit them
from this repo.

- `/home/blinken/claude-workspace/blinkenlight/research/00-positioning-options.md`
  — §5a DECISIONS LOG, including the lost-deal diagnosis and the
  credibility-stack-first principle.
- `/home/blinken/claude-workspace/blinkenlight/PLAN.md` — Phase 4
  "Credibility stack"; this work is Phase 4.
- `/home/blinken/claude-workspace/blinkenlight/research/04-ceng-pathway.md`
  — relevant to clause 7.2 (competence). CEng (Chartered Engineer) is
  NOT a prerequisite for ISO 9001.
- `/home/blinken/claude-workspace/blinkenlight/research/05-design-escrow.md`
  — methodology for grounding recommendations in contractual reality.
- `/home/blinken/Documents/blinkenlight/BLINKENLIGHT Ltd - Terms of business - Design services v2.1.pdf`
  — the canonical contract. Clause 37 grants full IP (Intellectual
  Property) assignment on payment; clause 36 retains pre-contract IP;
  no post-delivery maintenance obligation; no escrow/continuity clause
  yet. Each ISO 9001 clause must be reconciled with this contractual
  reality.

## Company facts (use only these for company info)

- BLINKENLIGHT Ltd, UK Radio-Frequency (RF) and electronics R&D
  (Research & Development) consultancy.
- Own RF/EMC (Electromagnetic Compatibility) lab at Unit 309 The Pill Box,
  115 Coventry Road, London E2 6GH.
- Company no. 13110356.
- Sole operator: Patrick Coleman. BEng (Bachelor of Engineering,
  Mechatronics) + BSc (Bachelor of Science, Computer Science). Not a
  Chartered Engineer.
- Own product lines:
  - Paradar — LoRa (Long Range radio) and aviation antennas; a handheld
    Automatic Dependent Surveillance — Broadcast (ADS-B) flight
    instrument.
  - Bluespot — 4G/5G broadband antennas.
- Antenna work for a High-Altitude Pseudo-Satellite (HAPS) aerospace
  programme. **The end customer must not be named** in any QMS document.
- InvenTree is the existing inventory / purchasing / sales system. It
  feeds the records spine for clauses 8.4 (purchasing & supplier
  control), 8.5.2 (identification & traceability), 8.6 (release of
  products), and 7.5 (documented information for stock/BOMs (Bills of
  Materials)).
- The published engineering process — scope → design → prove → handover —
  is the backbone for clauses 8.1–8.6 and clause 9.

## QMS architecture: Git-on-GitHub

The QMS lives in this repository:

- **Source of truth:** markdown files in this Git repository.
- **Render:** GitHub private-repo web UI. Auditors are granted a
  time-limited read-only collaborator seat for the audit period.
- **Approval record:** signed Git commits authored by Patrick. The
  documented self-approval procedure (to be drafted in `DOC-CONTROL.md`)
  describes how this satisfies clause 7.5.2.
- **Master Document List:** `MASTER-DOCUMENT-LIST.md` at the repo root,
  generated or hand-maintained from per-document frontmatter.
- **Audit Pack:** rendered PDF snapshots in `audit-pack/YYYY-MM-DD/`,
  produced from `main` HEAD via a build script before each audit. The
  PDFs carry document ref, version, approval date, approver, and commit
  hash in the footer.
- **Records:** per-engagement folders under `records/<project>/`; the
  calibration register and CAPA (Corrective and Preventive Action) log
  live at the repo root as living documents.

## Navigation

- `PLAN.md` — phased roadmap and open decisions.
- `GAPS.md` — every piece of real input still needed from Patrick.
- `research/` — research notes that feed the plan but are not part of
  the QMS itself (kept for traceability of decisions).
- Future: `manual/` (Quality Manual), `procedures/`, `records/`,
  `templates/`, `audit-pack/`, `MASTER-DOCUMENT-LIST.md`,
  `DOC-CONTROL.md`.

## Working conventions

- One document per file. Each controlled document carries YAML
  frontmatter: `id`, `title`, `version`, `approved_date`, `approver`,
  `supersedes` (commit hash), `clause_refs`.
- Commits that change a controlled document use the form:
  `<DOC-ID> v<N>, <short description>`.
- Never run `git` commands without explicit user approval.
- Never draft a procedure to fill a gap — find a real engagement that
  exercises the clause, draft the procedure against it, then generalise.
- When the user references items in `GAPS.md`, treat them as a working
  punch list; remind the user about outstanding items occasionally.

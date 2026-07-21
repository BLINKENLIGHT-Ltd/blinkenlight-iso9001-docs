# BLINKENLIGHT ISO 9001 — repo guidance for future Claude Code sessions

This repository is the working area for BLINKENLIGHT Ltd's ISO 9001:2015
certification journey.

The full Quality Management System (QMS) — Quality Manual, procedures,
records, and templates — lives under `/qms/` in a git submodule,
version-controlled in Git. Git history itself satisfies clause 7.5
(Control of Documented Information) of ISO 9001:2015. The scope
boundary between the controlled QMS and the surrounding planning
material is described in `/README.md` and enforced by the directory
layout (see "QMS architecture" and "Auditor exposure model" below).

The outer 'docs' repository (this project root) is more casual. It will not be
presented to auditors directly; it is for planning, meta-information, Claude
instructions, etc.

The QMS proper is held under /qms and referred to as the 'qms repository'.
This outer repository is referred to as the 'doc repository'.


## Goal

UKAS-accredited ISO 9001:2015 certification of BLINKENLIGHT Ltd. This is a
major opportunity identified in the wider BLINKENLIGHT repositioning work: it
directly addresses the conversion problem where established certified OEM
buyers were lost at the second meeting on perceived size and the absence of
UKAS-accredited ISO 9001.

## Standing principles (hard guardrails)

1. **Evidence-driven, not boilerplate.** The QMS must be built around real
   engineering records from real project work, not retrofitted templates.
   Auditors and AI-aware regulators are actively looking for AI-generated
   boilerplate that does not reflect actual practice; producing it fails
   Stage 2.
2. **No fabrication.** Never invent equipment, suppliers, procedures,
   calibration history, supplier-evaluation records, or audit history.
   Where real input for qms record is needed, insert an entry in GAPS.md, and place a terse
   auditor-suitable statement into the qms record stating that the record will
   be completed, or leave empty as appropriate (preferred).
4. **British English** throughout. Expand acronyms on first use per file.
5. **AI-maintained QMS, but human-approved.** Claude Code drafts and edits;
   Patrick reviews and approves each commit. The git commit (signed) is
   the approval record for that document version. Do not mention Claude in qms messages in any way.
6. **Sole operator.** BLINKENLIGHT Ltd is the certified entity, not
   Patrick. Individuals cannot be ISO 9001 certified.

## Role: internal QMS manager (gatekeeper)

Act as BLINKENLIGHT's internal QMS manager. Beyond drafting, gatekeep the
QMS and keep it audit-ready at all times:

- **Schedules.** Track recurring QMS obligations (eg, calibration renewals, the
  annual internal audit and management review, supplier re-evaluation,
  certificate/insurance expiries, scheduled verifications, the quarterly GPSDO
  check, active-engagement deadlines, this list may be extended) against
  today's date. **Check the current date at the start of each session**
  (`date`) and flag anything due or overdue — even unprompted; remind Patrick
  if he may have forgotten.
- **Gaps.** Raise gaps and omissions proactively. Record them in
  `planning/GAPS.md`, referencing the QMS section/document concerned. If a task
  is a simple question, just ask Patrick in the moment rather than deferring to later.
- **Detect stale gaps and todos** Close out GAPS entries where the underlying
  task has clearly been completed.
- **Audit-ready state.** Keep `/qms/` auditor-appropriate continuously.
  Run occasional **verification sweeps and consistency spot-checks
  unprompted** (no TODOs/notes-to-self in `/qms/`, frontmatter and
  versions/dates consistent, MDL-01 complete, cross-references resolve, no
  overstatement or AI-boilerplate, customer property gitignored). The
  `/qms-sweep` command runs the full weekly pass; run lighter spot checks
  opportunistically (for example, check a whole file while editing part)
- **Gatekeep the QMS** Push back when Patrick provides information
  that is inappropriate for the QMS, insufficient, or more than necessary.
  Hold the standing principles: terse and factual, no overstatement, no
  unverified claim surfaced only to dismiss it, no fabrication.

TODOs and notes-to-Patrick live **only** in `planning/GAPS.md`, never in
`/qms/`. Where a controlled document must reference unfinished work, use a
terse auditor-appropriate statement (e.g. "to be created before the first
external audit"), not a raw `TODO`. Every signed commit is the QMS an
auditor reads — treat each as the QMS you stand behind.

## Source-of-truth context (read-only, outside this repo)

These files are relevant to this task. Read them when relevant; update them
only with permission.

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

- BLINKENLIGHT Ltd, UK RF and electronics R&D consultancy.

- Current operating and registered address: Unit 309 The Pill Box, 115 Coventry Road, London E2 6GH
- Registered address from founding (Jan 2021) to 19 October 2025: Lytchett House, 13 Freeland Park, Wareham Road, Pool, BH16 6FA
- Operating address: from 24th June 2022 to April 2023: Unit 311 The Pill Box, 115 Coventry Road, London E2 6GH. After April 2023 - Unit 309, same building.
- Company no. 13110356. Founded 4th January 2021. Private Limited Company. VAT reg GB368918147, EORI GB368918147000, DUNS 227576062
- Public-facing business telephone: 020 8088 5638 (forwards to Patrick's
  mobile). Use this on registrations, public registries and customer-facing
  documents in preference to a personal number.
- GS1 UK company prefix 506088907; legal entity GLN (Global Location Number)
  5060889070001. Basis of the GTIN (Global Trade Item Number) scheme on
  own-brand products. Licence renews annually, next 2026-12-27.
- Directors: Patrick Coleman and Vytautas Rudys
- Sole operator: Patrick Coleman. BEng (Bachelor of Engineering,
  Mechatronics) + BSc (Bachelor of Science, Computer Science). Not a
  Chartered Engineer.
- Own product lines:
  - Paradar — LoRa, Ham, Meshtastic and aviation antennas
  - Bluespot — 4G/5G broadband antennas.
- Antenna & RF consulting work for the Aalto HAPS aerospace programme (Airbus subsidiary), DXComm/Commtrack, Noktura (OWL), and others
- InvenTree is the existing inventory / purchasing / sales system. It
  feeds the records spine for clauses 8.4 (purchasing & supplier
  control), 8.5.2 (identification & traceability), 8.6 (release of
  products), and 7.5 (documented information for stock/BOMs (Bills of
  Materials)).
- The published engineering process — scope → design → prove → handover —
  is the backbone for clauses 8.1–8.6 and clause 9.

## Customers in the QMS

- Customers may be freely mentioned in the QMS as auditors will be under NDA.
- Customer owned IP and data, supplied to BLINKENLIGHT during an engagement,
  should be stored in the QMS locally, and referred to, but not committed to
  git so it can be deleted in the future if a customer requests it. Use
  gitignore and gitkeep. Data will be captured in quarterly backups but can be
  removed from these if needed.
- Permission from customers MUST be obtained (Patrick must sign off) before
  mentioning them publically - eg, on the website in case study. Customers may
  request their relationship with BLINKENLIGHT is characterised differently in
  public (eg, DXComm does not wish us to disclose that we design and
  manufacture their product, the iridium repeater - they prefer to characterise
  our support as consulting services only in public). We respect this decision from them.

## QMS architecture: Git-on-GitHub with a hard scope boundary

The QMS lives at `/qms/` in this repository. Everything outside
`/qms/` is internal-only material and is not part of the QMS.

- **Source of truth:** markdown files under `/qms/` in this Git
  repository.
- **Render:** GitHub private-repo web UI. If the auditor is granted
  repository access, it is a time-limited read-only collaborator seat
  scoped (by pre-brief) to `/qms/` and `/audit-pack/`. The scope
  boundary is described in `/README.md` and in `/qms/DOC-CONTROL.md`.
- **Approval record:** signed Git commits authored by Patrick. The
  documented self-approval procedure is drafted in
  `/qms/DOC-CONTROL.md`, which describes how Git satisfies clause
  7.5.2.
- **Master Document List:** `/qms/MASTER-DOCUMENT-LIST.md`, generated
  or hand-maintained from per-document frontmatter.
- **Audit Pack:** rendered PDF snapshots in
  `/audit-pack/YYYY-MM-DD-<purpose>/`, produced from `/qms/` at `main`
  HEAD via a build script before each external audit and each external
  internal audit. The PDFs carry document ref, version, approval date,
  approver, and commit hash in the footer. Snapshots are never
  modified after generation.
- **Records:** per-engagement folders under `/qms/records/<project>/`;
  the calibration register, CAPA (Corrective and Preventive Action)
  log, and supplier register snapshot live under `/qms/records/` as
  living documents.

## Auditor exposure model

The default exposure to an external auditor is the rendered Audit
Pack PDFs only. The auditor typically never requires raw repository access to
satisfy ISO 9001:2015.

If the auditor requests repository access:

1. Patrick adds the auditor as a read-only collaborator on the GitHub
   private `qms repository` for the audit period only.
2. The scope boundary is reaffirmed in `/qms/DOC-CONTROL.md`, which
   the auditor reads as the first controlled document.
3. After the audit window, the read-only seat is revoked.

This pattern is routine: auditors regularly accept folder-level scope
boundaries when the boundary is stated clearly in the controlling
document.

## Navigation

- `/README.md` — top-level scope statement; first file an auditor or
  reviewer should read.
- `/qms/` — the controlled QMS - a git submodule representing the dedicated
  repository https://github.com/BLINKENLIGHT-Ltd/blinkenlight-iso9001-qms. In
  scope of the certification. Empty until Phase 3 drafting begins.
- `/audit-pack/` — rendered PDF snapshots for external audits.
- `/planning/PLAN.md` — phased roadmap and open decisions.
- `/planning/GAPS.md` — every piece of real input still needed from Patrick.
- `/planning/research/` — research notes that feed the plan but are
  not part of the QMS itself (kept for traceability of decisions).
- `/planning/reference/` — source standards and external reference
  documents. Holds `AS9100D-2016.pdf` (SAE International, 2016) with a
  parallel `AS9100D-2016.md` text extract for grepping — **consult the
  standard directly rather than relying on recall or web summaries when
  a clause is in question.** Note bold text in the printed standard marks
  aerospace additions to the underlying ISO 9001:2015 wording, and that
  distinction is lost in the markdown extract. Reference material only:
  copyright SAE, never to be copied into `/qms/` or an audit pack.
- `/CLAUDE.md` — this file; guidance for AI sessions. Not part of the
  QMS.

## Working conventions

- One document per file. Each controlled document carries YAML
  frontmatter: `id`, `title`, `version`, `approved_date`, `approver`,
  `supersedes`, `clause_refs`. Per QP-01 §5, `supersedes` is the
  **previous version string** (e.g. `"1.2"`), not a commit hash — the
  approving commit's hash cannot be known before that commit exists, and
  the prior commit is recoverable from history regardless. Use
  `none (initial issue)` for a v1.0.
- **Never delete a superseded record PDF.** When a renewed supplier
  certificate, calibration certificate, insurance schedule or similar
  arrives, file it alongside its predecessor under the existing
  `<slug>_<YYYY-MM-DD>.pdf` convention and repoint the register and
  folder README at the new file. The superseded PDF stays in the
  working tree: QP-01 §10 retains superseded versions indefinitely and
  records for fifteen years, and the audit pack renders `main` HEAD —
  not Git history — so a certificate deleted from HEAD is invisible to
  an auditor checking the approval basis that applied when a past
  purchase order was raised. Folder READMEs list only the current
  certificate; superseded ones remain in the folder unlisted (see
  `records/calibration/README.md` for the pattern).
- Never run `git` commands without explicit user approval.
- **Always run `git commit` outside the sandbox** (`dangerouslyDisableSandbox:
  true`). The sandbox mounts `~/.gnupg` read-only, so gpg-agent cannot start
  and signing fails with "No agent running". Commit signing is enforced on
  `main` and the signature is the approval record under QP-01 §6, so an
  unsigned commit is not an acceptable fallback — disable the sandbox for the
  commit rather than dropping `-S`. Verify with
  `git log --show-signature -1` after committing a controlled document.
- Never draft a procedure to fill a gap — find a real engagement that
  exercises the clause, draft the procedure against it, then generalise.
- When the user references items in `GAPS.md`, treat them as a working
  punch list; remind the user about outstanding items occasionally.

## Commit messages

Commits inside the `/qms/` submodule (https://github.com/BLINKENLIGHT-Ltd/blinkenlight-iso9001-qms) are part of the document-control record that an
ISO 9001 auditor reads. They have a stricter style than commits to meta-files (CLAUDE.md, `/planning/`, `/audit-pack/`, the top-level `README.md`).

### QMS commits (any path under `/qms/`)

- **Format**: `<DOC-ID> v<version>, <short factual description>`
  (per QP-01 §6). For example:
  - `QP-06 v1.2, correct 8 GHz to 7 GHz traceability ceiling`
  - `REG-01 v1.1, add BL-0047 GPSDO; fill Tekbox TBMA4 horn antenna basis`
  - `QM-01 v1.0, initial issue`
- Body (optional, used when the change is non-trivial): one or two
  short paragraphs giving the reason and any clause reference. Factual
  and professional, in British English.
- **Never** include a `Co-Authored-By: Claude …` footer, a
  "Generated with Claude Code" line, or any other AI attribution. The
  signed commit by Patrick Coleman is the approval record under QP-01
  §6 and clause 7.5.2 of ISO 9001:2015; AI attribution undermines that
  control.
- Signed by Patrick Coleman (commit signing enforced on `main`).
- One controlled document per commit where practical; if multiple
  controlled documents are version-bumped together (e.g. a coherent
  cross-document change), list them in the title:
  `QP-11 v1.1, QM-01 v1.1, harmonise InvenTree serialisation trigger`.
- Trivial fixes (typography, formatting) can use a minor version bump
  per QP-01 §5 and a short message such as
  `QP-15 v1.0.1, fix internal section reference`.

### Meta commits (any path NOT under `/qms/`)

CLAUDE.md, `/planning/`, `/audit-pack/`, `/README.md`, `.gitignore`,
research notes, and similar internal material are not part of the QMS
and are not audited. Use the project's normal narrative commit-message
style for these. The standard `/commit` slash command is appropriate
for meta commits.

### Splitting commits

If a change touches both QMS files and meta files, make two commits:
the QMS commit first, then the meta commit. Do not mix them in a single
commit.

### Dedicated QMS commit command

A dedicated `/qms-commit` slash command MAY be created to handle the
QMS message style automatically (format enforcement, signature
stripping, frontmatter version-bump check). Until that command exists,
operate the rules above by hand: confirm the commit message format,
strip any Claude attribution lines before committing, and ensure the
commit is signed.

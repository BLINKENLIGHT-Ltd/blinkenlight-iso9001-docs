# BLINKENLIGHT Ltd — ISO 9001:2015 Roadmap

Compressed, sole-operator roadmap from initiation to UKAS-accredited
certification. No time estimates. Phases are ordered by dependency.

## Todo list

- [x] Foundational read of the standard and contractual baseline
- [x] QMS architecture decision (Git on GitHub private repo, markdown
      source, rendered Audit Pack PDFs)
- [x] Internal-audit objectivity decision (external internal auditor
      annually — see Decisions below)
- [ ] Phase 1: clause-by-clause gap analysis against current state
- [ ] Phase 2: certification body shortlist quoted and chosen
- [ ] Phase 2: external internal auditor identified and engaged
- [ ] Phase 2: calibration provider chosen and current-state register
      established
- [ ] Phase 3: QMS drafting against real project evidence
- [ ] Phase 3: ≥3 months of operating records before booking Stage 1
- [ ] Phase 4: Stage 1 audit
- [ ] Phase 4: Stage 2 audit → certificate

## Standing decisions

1. **Scope:** Design and development of Radio-Frequency (RF) and
   electronics products and services, including own-brand product lines
   (Paradar, Bluespot). Operated from Unit 309 The Pill Box, London
   E2 6GH.
2. **Certification:** UKAS-accredited only. Top candidates to quote:
   NQA, Alcumus ISOQAR, British Assessment Bureau (now Amtivo). See
   `planning/research/01-certification-bodies.md`.
3. **Storage:** Git, this repository, hosted on GitHub as a private
   repository. QMS lives under `/qms/`; planning and research material
   under `/planning/` is out of scope. Auditor access (if granted at
   all) is via time-limited read-only collaborator seat scoped by
   pre-brief to `/qms/` and `/audit-pack/`. Default exposure is the
   rendered Audit Pack PDFs from `main` HEAD only.
4. **Internal-audit objectivity (clause 9.2.2 c):** External internal
   auditor engaged annually. Sole-operator self-audit is not defensible
   under "objectivity and impartiality" and is not used.
5. **AI-maintained, human-approved.** Claude Code drafts and edits;
   Patrick reviews and approves each commit. Signed commits by Patrick
   are the approval record.

## Phase 0 — Foundations (complete)

- ISO 9001:2015 read in full (the standard is ~20 pages of normative
  clauses; companion is BS EN ISO/TS 9002:2016 "Quality management
  systems — Guidelines for the application of ISO 9001:2015").
- BLINKENLIGHT Terms of Business v2.1 reviewed. Each ISO 9001 clause
  must be reconciled against:
  - Clause 37: full IP (Intellectual Property) assignment on payment.
  - Clause 36: pre-contract IP retained by BLINKENLIGHT.
  - No post-delivery maintenance obligation.
  - No escrow/continuity clause yet (open question — see
    `~/claude-workspace/blinkenlight/research/05-design-escrow.md`).
- AI-maintained-but-evidence-driven principle confirmed. No retrofitted
  boilerplate.
- Git-on-GitHub architecture confirmed (see CLAUDE.md → "QMS
  architecture").

## Phase 1 — Clause-by-clause gap analysis

One document, not four. Walks ISO 9001:2015 clauses 4 through 10 and
for each records:

- What the clause requires (one sentence).
- How it scales for a solo RF/electronics R&D consultancy (proportionality).
- The artefact, record, or process that satisfies it.
- What InvenTree, the published engineering process, and the Terms of
  Business v2.1 already deliver.
- Have / partial / gap, with the action to close it.

Heavy lifts to flag explicitly inside that document:

- **Clause 8.3 (Design and development)** — the meatiest clause for an
  engineering consultancy. Design inputs, design reviews, design
  verification, design validation, design changes. Must integrate with
  the published scope → design → prove → handover process.
- **Clause 7.1.5 (Monitoring and measuring resources)** — calibration.
  Distinguish calibration to a traceable standard from verification.
  This is **not** ISO 17025 (laboratory accreditation); the bar is
  lower but still load-bearing.
- **Clause 7.2 (Competence)** — solo operator. CEng (Chartered Engineer)
  is not required. Competence evidence comes from degrees, the
  engineering process, demonstrable engagement records, and the
  published technical history.
- **Clause 8.4 (Control of externally provided processes, products and
  services)** — supplier control. InvenTree carries most of this.
- **Clause 9.1.2 (Customer satisfaction)** — process required, not
  necessarily formal surveys. Post-engagement debriefs documented as
  records will satisfy it.
- **Clause 9.2 (Internal audit)** — external internal auditor handles
  this. See Decisions above.
- **Clause 9.3 (Management review)** — annual, documented. For a sole
  operator this is a structured self-review against fixed inputs
  (audit results, customer feedback, nonconformities, supplier
  performance, calibration status, resource needs).
- **Clause 10.2 (Nonconformity and corrective action)** — CAPA log
  required. Must be populated with real events, including small ones.
  An empty CAPA log is itself a nonconformity at Stage 2.

Output: `planning/gap-analysis.md`, with the table and a "heavy lifts"
summary section. The gap analysis is itself a planning artefact, not
a QMS document; it informs which procedures go into `/qms/` in
Phase 3 but is not controlled.

## Phase 2 — Decisions to close before drafting begins

Three explicit choices Patrick must make. Each blocks drafting work in
Phase 3 and each should be reflected as a closed item in `GAPS.md`.

### 2a. Certification body

Quote at least three UKAS-accredited bodies. Verify accreditation
status directly against https://www.ukas.com/find-an-organisation/ —
do not rely on the body's own marketing. See
`planning/research/01-certification-bodies.md` for the recommended
shortlist, quotes checklist, and the comparison criteria.

Decision criteria, ordered:
1. UKAS-accredited for ISO 9001:2015 (non-negotiable).
2. Reasonable cost profile across the 3-year cycle for a one-site,
   low-risk solo.
3. Familiarity with RF / electronics / aerospace-adjacent scope.
4. Remote-audit policy (matters for surveillance years).
5. Reputation with the target buyers (Trig Avionics, Redtail
   Telematics, defence-adjacent OEMs).

### 2b. External internal auditor

Engage a freelance ISO 9001 internal auditor on a recurring annual
basis. Required by Decision 4. Selection criteria:

- Lead Auditor qualification (ISO 9001 Lead Auditor course, typically
  IRCA (International Register of Certificated Auditors) certified).
- Independent of the chosen certification body (impartiality
  requirement under clause 9.2.2 c) — explicitly check this in the
  engagement letter).
- Experience with engineering / R&D / electronics scope.
- Comfortable with a Git-hosted markdown QMS and able to audit it in
  that form (or willing to be walked through the rendered Audit Pack).

Indicative cost: £600–£1,500 per annual internal audit for a solo.
See `GAPS.md`.

### 2c. Calibration provider

A UKAS-accredited calibration laboratory (ISO/IEC 17025) for the lab's
measurement instruments. Distinguish between:

- **Calibration** — traceable, certificated, against a national
  standard. Required for instruments whose measurements appear in
  controlled records (design verification, EMC pre-compliance results
  cited to a customer or in a Declaration of Conformity).
- **Verification** — in-house check that an instrument is operating
  within tolerance against a known reference. Acceptable for many
  instruments not used in controlled measurements.

Cadence per instrument class is set in the calibration register
(populated in Phase 3 once Patrick provides the equipment inventory —
see `GAPS.md`). Typical cadence is annual for high-value RF
instruments (Vector Network Analyser (VNA), Spectrum Analyser, Signal
Generator) and longer or verification-only for lower-stakes
instruments. The register itself is a controlled document.

Indicative cost is £500–£2,000 per year depending on instrument count
and lab tier. To be quoted alongside the equipment inventory.

## Phase 3 — QMS drafting against real project evidence

Drafting only begins once Phase 2 decisions are closed. Each procedure
is drafted against a **real BLINKENLIGHT engagement that exercises the
clause it satisfies**. No template-first, retrofit-evidence-later. This
is the explicit lesson from the AI-boilerplate red-flag literature.

Order of drafting (dependency-ordered):

1. **`/qms/DOC-CONTROL.md`** — the controlled document that explains
   how Git satisfies clause 7.5 and that defines the `/qms/` scope
   boundary. Must exist before anything else is controlled, because
   auditors will read it first to understand the tool and the scope.
2. **`/qms/MASTER-DOCUMENT-LIST.md`** — index, populated as documents
   are added.
3. **Quality Manual** — small. Scope, context, leadership commitment,
   process map. The published scope → design → prove → handover process
   is the spine.
4. **Procedures**, one per heavy-lift clause, in this order:
   - Design and development (8.3) — drafted against a current Paradar
     or HAPS-programme engagement.
   - Purchasing & supplier control (8.4) — drafted against the
     existing InvenTree supplier list.
   - Monitoring and measuring resources / calibration (7.1.5) —
     drafted against the actual lab inventory.
   - Customer satisfaction (9.1.2) — drafted against a real
     post-engagement debrief.
   - Nonconformity and corrective action (10.2) — drafted against at
     least one real prior incident or near-miss.
   - Internal audit (9.2) — drafted to describe the external internal
     auditor engagement.
   - Management review (9.3) — drafted to describe the annual review
     procedure.
5. **Templates**: design review minute, design verification record,
   design validation record, supplier evaluation record, calibration
   certificate index entry, CAPA entry, internal-audit report,
   management-review minute, customer-satisfaction record.
6. **Records spine**: per-engagement folders under `/qms/records/`;
   the live calibration register; the live CAPA log; the live
   supplier register (or an exported snapshot of InvenTree). All
   under `/qms/` and therefore in scope for the certification.

Operating period: the QMS must be **operated** for at least 3 months
(some bodies prefer 6) before Stage 1 is bookable. Real records
generated in that period are what the Stage 2 audit samples.

## Phase 4 — Audit

1. **Stage 1** — readiness review, often remote, half-day to one day.
   Auditor confirms the QMS exists, has been operated for the required
   period, and the documented information is structurally sound. Any
   findings here are addressed before Stage 2.
2. **Stage 2** — main assessment. On-site at Unit 309, typically 1–2
   days. Auditor samples real records across the clauses, walks the
   lab, interviews Patrick, reviews calibration certificates and
   internal-audit reports. Major nonconformities block certification;
   minor ones close out post-audit.
3. **Certificate issued.** Valid 3 years. Buyer-facing brand language
   may then state "ISO 9001 certified" with the certification body and
   UKAS accreditation mark per the body's brand rules. Until then, the
   "not yet held" rule from the brand language guide applies — any
   client-facing copy must not imply certification.

## Phase 5 — Ongoing operation

The cycle continues:
- Year 1 surveillance audit.
- Year 2 surveillance audit.
- Year 3 recertification audit (full).
- Annual external internal audit (separate from the certification
  body's audits).
- Annual management review.
- Calibration on the published cadence.
- CAPA log maintained continuously.
- Repository remains the source of truth; Audit Pack regenerated
  before each external visit.

## What this plan deliberately omits

- The "spawn a /loop cron job for management-review prep" idea from
  the original brief. Annual events live in a calendar.
- Cyber Essentials, ISO 27001 readiness, and JOSCAR. These belong to
  the wider credibility stack and are tracked elsewhere
  (`~/claude-workspace/blinkenlight/PLAN.md`). They are not in scope
  here.
- A separate `04-qms-architecture.md` research document. The
  architecture is documented in `CLAUDE.md` and will be expanded into
  `DOC-CONTROL.md` in Phase 3.
- A separate `02-clause-map.md` research document. The clause-by-
  clause walk is the Phase 1 `gap-analysis.md` deliverable.
- A separate `03-calibration.md` research document. Calibration is
  covered as Decision 2c and then as the calibration procedure in
  Phase 3.

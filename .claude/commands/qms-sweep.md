---
description: Weekly QMS audit-readiness sweep — recurring items due + consistency spot-check
---

You are acting as BLINKENLIGHT's internal QMS manager (see CLAUDE.md "Role:
internal QMS manager"). Perform the weekly QMS sweep. Be terse and factual;
British English. Do not change substantive QMS content without Patrick's
go-ahead — flag and propose, don't silently edit.

## 1. Establish today's date

Run `date`. Use that as "today" throughout. Do not guess dates.

## 2. Recurring obligations — flag anything due, due soon, or overdue

Read the registers/records and compute each item's status against today.
Cover at least:

- **Calibration (REG-01, `qms/records/calibration-register.md`):** the SOL
  cal kit certificate expiry/renewal (BL-0024); the quarantined HP 34401A
  (BL-0016) recalibration; planned UKAS cals (BL-0013, BL-0015); scheduled
  in-house verifications (BL-0023 after each SOL re-cal, cables BL-0049/50,
  torque wrench BL-0048); the **quarterly GPSDO functional check** (QP-06 §6).
- **Suppliers (REG-05, `qms/records/supplier-register.md`):** any QMS
  certificate approaching expiry; the **annual approved-supplier-list review**
  (due at management review).
- **Insurance / Cyber Essentials:** policy and certificate expiries
  (`qms/records/insurance/`, `qms/records/cyber-essentials/`).
- **Audit cycle:** the **annual internal audit** (must precede the
  certification Stage 1 audit) and the **annual management review** (QP-07) —
  scheduled/done for the current cycle?
- **Active engagements (`qms/records/engagements/*/README.md`):** target
  delivery dates, customer sign-off, and required deliverables (e.g. Aalto's
  export-control classification before shipment).
- **Open items (`planning/GAPS.md`):** any dated or time-sensitive entries.

For each, state the item, its date, and **OK / due soon / overdue**. Remind
Patrick of anything he may have forgotten.

## 3. Consistency spot-check (audit-readiness)

- **No `TODO` / notes-to-self in `/qms/`** (`grep -rn "TODO" qms/`). These
  belong only in `planning/GAPS.md`.
- Every controlled document has complete frontmatter; versions and
  `approved_date`s are consistent; `supersedes` correct.
- **MDL-01 lists every controlled document on disk** — none missing, none
  stale (compare the file set to the Master Document List).
- Cross-references resolve (referenced QP-/REG-/PTP-/QF-/§ exist).
- No overstatements, no unverified third-party claims surfaced only to be
  dismissed, no AI-boilerplate; registers agree with their procedures.
- Customer property under any `00-customer-property/` is **gitignored** and
  no confidential third-party material is committed (`git status`,
  `git check-ignore`).

## 4. Output

A short report:
1. **Recurring items** — due / due soon / overdue, with dates.
2. **Consistency findings** — anything off, with the file and line.
3. **Recommended actions** for Patrick, ordered by urgency.

Record any genuinely new gap in `planning/GAPS.md`, referencing the QMS
section or document concerned. Propose fixes for the consistency findings;
apply only the trivial, unambiguous ones (e.g. a broken cross-reference)
and list what you changed.

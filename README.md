# BLINKENLIGHT Ltd — ISO 9001:2015 Quality Management System

This repository hosts BLINKENLIGHT Ltd's ISO 9001:2015 (International
Organisation for Standardisation Quality Management Systems) Quality
Management System (QMS).

## Scope boundary

- **`/qms/`** — the controlled QMS. Every document under this path is
  in scope of the certification. This is what the auditor sees, via
  the rendered Audit Pack PDFs in `/audit-pack/`.
- **`/audit-pack/YYYY-MM-DD/`** — rendered PDF snapshots of `/qms/` at
  `main` HEAD, produced before each external audit. PDFs carry
  document reference, version, approval date, approver, and commit
  hash in the footer.
- **`/planning/`** — internal planning, research, and initiation
  artefacts. **Not part of the QMS.** Out of scope for the
  certification. Retained for internal traceability of decisions.
- **`/CLAUDE.md`** — guidance for AI-assisted editing of this
  repository. Not part of the QMS.

The auditor's interaction with this repository is normally via the
Audit Pack PDFs only. If full repository access is granted, the same
scope boundary applies: only `/qms/` and the rendered Audit Pack are
within the audited QMS.

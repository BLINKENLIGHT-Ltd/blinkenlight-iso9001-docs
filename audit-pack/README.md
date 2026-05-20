# /audit-pack/ — rendered audit packs

Each subdirectory under this path is a dated snapshot of the QMS
(Quality Management System) at a point in time, produced from the
`main` branch HEAD shortly before an external audit (Stage 1, Stage 2,
surveillance, recertification) or before an external internal audit.

## Contents of a snapshot

- PDF rendering of every controlled document in `/qms/` at the snapshot
  commit. PDFs carry document reference, version, approval date,
  approver, and source commit hash in the footer.
- A manifest file listing every PDF, its source path, its frontmatter
  metadata, and the source commit hash.
- A copy of the Master Document List at the snapshot commit.

## Naming

`YYYY-MM-DD-<purpose>/` — e.g. `2026-09-15-stage-1/`,
`2027-09-01-surveillance-1/`, `2026-08-20-internal-audit/`.

## Generation

The rendering script (to be written in Phase 3 — see
`/planning/GAPS.md`) is run by Patrick from the `main` branch HEAD.
The output of any prior run is preserved unchanged; snapshots are
never modified after generation.

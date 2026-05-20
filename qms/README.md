# /qms/ — controlled Quality Management System documents

Every document under this directory is part of BLINKENLIGHT Ltd's
ISO 9001:2015 Quality Management System (QMS) and is in scope of the
certification. Documents elsewhere in the repository — including
`/planning/` and `/CLAUDE.md` — are not part of the QMS.

The directory is currently empty. Population begins in Phase 3 of the
roadmap (see `/planning/PLAN.md`), once the Phase 2 decisions are
closed (certification body, external internal auditor, calibration
provider).

## Planned layout (populated as drafting progresses)

```
/qms/
  DOC-CONTROL.md             First controlled document. Defines how
                             Git satisfies clause 7.5 (Control of
                             Documented Information): identification,
                             approval, version control, retention,
                             obsolete-version management, and the
                             scope boundary above.
  MASTER-DOCUMENT-LIST.md    Index of every controlled document, with
                             reference, title, current version, and
                             approval date.
  manual/                    Quality Manual: scope, context,
                             leadership commitment, process map.
  procedures/                Documented procedures, one per clause or
                             clause cluster.
  templates/                 Record templates (design review, design
                             verification, supplier evaluation, CAPA
                             entry, internal-audit report,
                             management-review minute, customer-
                             satisfaction record).
  records/                   Per-engagement records and living
                             registers (calibration register, CAPA
                             log, supplier register snapshot).
```

## Approval record

The approval record for each version of a controlled document is the
signed Git commit, authored by Patrick Coleman, that introduced or
amended it. The procedure for this is documented in `DOC-CONTROL.md`.

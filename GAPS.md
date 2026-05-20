# GAPS — Patrick input required

Live punch list of items where real input is needed before the QMS
(Quality Management System) can be drafted. Each item blocks at least
one downstream activity in `PLAN.md`. Future Claude Code sessions
should remind Patrick occasionally about anything still open here.

## Decisions to close (Phase 2 of PLAN.md)

- [ ] **Certification body chosen.** Quotes obtained from at least
      NQA, Alcumus ISOQAR, and British Assessment Bureau (Amtivo).
      UKAS accreditation verified directly against ukas.com for each
      before quoting. See `research/01-certification-bodies.md` for
      the quotes checklist.
- [ ] **External internal auditor engaged.** Annual cadence, IRCA
      (International Register of Certificated Auditors) Lead Auditor
      qualified, independent of the chosen certification body,
      experienced with engineering / electronics scope, willing to
      audit a Git-hosted markdown QMS via the rendered Audit Pack.
      Indicative cost £600–£1,500 per audit. Selection method:
      shortlist three candidates, interview, request a fixed quote
      for the first internal audit plus indicative recurring fee.
- [ ] **Calibration provider chosen.** UKAS-accredited calibration
      laboratory (ISO/IEC 17025) appropriate to the lab's instrument
      mix. Quote required once the equipment inventory below is
      provided.

## Operational data needed from Patrick

- [ ] **Equipment inventory.** Complete list of measurement instruments
      in the Bethnal Green lab that could appear in controlled
      records. Include for each:
      - Manufacturer, model, serial number.
      - Date of purchase / acquisition.
      - Existing calibration certificates (provider, date, expiry,
        traceability statement).
      - Whether the instrument's measurements are used in
        customer-facing records (design verification, EMC
        (Electromagnetic Compatibility) results cited externally,
        DoC (Declaration of Conformity) evidence) — drives the
        calibration vs verification choice.
      - Expected use cases (Paradar, Bluespot, HAPS programme,
        consultancy work).

      Particular instruments expected to need attention:
      - Vector Network Analyser (VNA).
      - Spectrum analyser.
      - Signal generator.
      - Oscilloscope(s).
      - RF (Radio-Frequency) power meter(s).
      - EMC pre-compliance equipment (antennas, LISN (Line Impedance
        Stabilisation Network), pre-amps, near-field probes).
      - Any reference loads / attenuators / calibration kits used as
        traceability references.

- [ ] **Supplier list.** Current InvenTree suppliers used in real
      engagements. The InvenTree supplier registry will be the
      record-of-truth; this gap is about agreeing which suppliers
      are scope-relevant for the QMS (i.e. those whose outputs affect
      product quality) and which are not.

- [ ] **Named associate engineers, if any.** If any external
      engineers are engaged on consultancy work (even occasionally),
      they fall under clause 8.4 (control of externally provided
      processes) and clause 7.2 (competence). List names, scope, and
      relationship type.

- [ ] **Customer satisfaction data already held.** Any existing
      post-engagement feedback — emails, debriefs, repeat-business
      indicators, formal references. Clause 9.1.2 needs a process,
      not surveys, but evidence of past collection strengthens the
      case at Stage 2.

- [ ] **Past nonconformities and corrective actions.** Any prior
      issues — supplier failures, design defects fixed in revision,
      customer complaints, missed deadlines, lab incidents. Clause
      10.2 requires a CAPA log; populating it with real events is
      essential. An empty CAPA log is itself a nonconformity finding.

- [ ] **Past design changes worth referencing.** For clause 8.3.6
      (Design and development changes) — the Paradar and Bluespot
      product lines presumably have revision histories. The
      controlled record at Stage 2 will sample these; agreeing now
      which to use as reference cases will speed Phase 3 drafting.

## Contract / legal items to confirm

- [ ] **Escrow / continuity clause for Terms of Business v2.1.** Open
      question per
      `~/claude-workspace/blinkenlight/research/05-design-escrow.md`.
      Not strictly required for ISO 9001 but interacts with clause
      8.5.5 (post-delivery activities) and customer-confidence
      considerations. Solicitor review needed if added.

- [ ] **Brand language for "ISO 9001 certified" status.** Until
      certificate is held, the "not yet held" rule from the brand
      language guide applies. Patrick to confirm that all external
      copy (website, capability statements, proposals) currently
      complies and that a switch-over copy is drafted ready for the
      day the certificate arrives.

## Logistics

- [ ] **GitHub private repository created.** This local repo
      (`/home/blinken/Documents/blinkenlight/iso9001/`) needs to be
      pushed to a private GitHub repo so it can serve as the rendered
      auditor-readable surface. Per CLAUDE.md, no git commands
      without explicit approval — Patrick to run the push himself.

- [ ] **Backup remote.** Single GitHub remote is a single point of
      failure for the QMS itself, which is a clause 7.5.3.2 (storage
      and preservation) concern. Add at least one mirrored remote
      (e.g. a self-hosted git server, or a second cloud provider).

- [ ] **Audit Pack render script.** To be written in Phase 3.
      Produces PDF snapshots of all controlled documents from `main`
      HEAD into `audit-pack/YYYY-MM-DD/` with metadata footers (ref,
      version, approval date, approver, commit hash). Pandoc + a
      simple front-matter reader will do the job. Patrick can review
      the proposed script before it lands.

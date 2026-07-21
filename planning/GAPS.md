# GAPS — Patrick input required

Live punch list of items where real input is needed before the QMS
(Quality Management System) can be drafted. Each item blocks at least
one downstream activity in `PLAN.md`. Future Claude Code sessions
should remind Patrick occasionally about anything still open here.

## Decisions to close (Phase 2 of PLAN.md)

- [ ] **Certification body chosen.** Quotes obtained from at least
      NQA, Alcumus ISOQAR, and British Assessment Bureau (Amtivo).
      UKAS accreditation verified directly against ukas.com for each
      before quoting. See `planning/research/01-certification-bodies.md`
      for the quotes checklist.
      - Indicative pricing requested 2026-05-20 from NQA, Alcumus
        ISOQAR, and British Assessment Bureau (Amtivo). Awaiting
        response.
      - UKAS verification complete 2026-05-20. All three are
        accredited to ISO/IEC 17021-1:2015 and to ISO 9001:2015 with
        sector scopes that cover BLINKENLIGHT's work (IAF 19
        Electrical and optical equipment; IAF 33 Information
        technology; IAF 34 Engineering services). See
        `planning/research/01-certification-bodies.md` for the
        verified comparison table and per-body schedule references.
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

- [x] **Equipment inventory — high-level draft.** Captured at
      `planning/equipment-inventory.md` on 2026-05-20. In-scope and
      out-of-scope sets agreed. Open follow-ups listed below.

- [x] **Equipment inventory — asset tags applied.** Complete equipment
      list received 2026-06-03 with BL-NNNN asset tags aligned to the
      Xero fixed-assets register; REG-01 rebuilt to use BL-NNNN as the
      primary identifier with serial numbers, manufacturers and
      models filled in. Remaining open items split into the more
      specific tasks below.

- [x] **Reference horn antenna — basis confirmed.** Tekbox TBMA4
      (BL-0045, serial TBMA4200200). Manufacturer batch test report
      and data filed at
      `qms/records/calibration/tekbox-tbma4-horn-antenna-test-report/`.
      REG-01 BL-0045 records this as the factory characterisation
      basis. Confirming whether Tekbox publish a traceability
      statement for the batch report is tracked separately (below).

- [ ] **LISN (Line Impedance Stabilisation Network) — locate and
      assess.** Find the unit, record manufacturer / model / serial
      number, identify any existing calibration documentation, and
      decide its scope status. Held provisionally in scope pending
      this check; if indicative-only emissions audits never cite the
      LISN's readings externally, it can move to out-of-scope and
      be tagged accordingly. Update
      `planning/equipment-inventory.md` once located.

- [~] **RF (Radio-Frequency) reference cable and adapter register.**
      Sub-register started in REG-01 (`## RF reference cables and
      adapters`). Two Huber+Suhner TL-8A SMA(m)–SMA(m) 1.5 m leads
      (TL-8A-11SMA-11SMA-01500-51, H+S 85014638, RS 132-8154, to 8 GHz)
      tagged BL-0049/BL-0050 (sub-£200, not in Xero); datasheet filed
      at `qms/records/calibration/rf-cables/`. BL-0049/BL-0050 physical
      tags applied 2026-06-04; acquisition dates recorded (BL-0049
      2022-03-10, BL-0050 2021-12-09). Remaining: perform the first
      electrical verification check (after SOL kit re-cal), and add any
      adapters used in the chains.

- [x] **Order "not in cal scope" labels.** Ordered 2026-06-03;
      applied 2026-06-04 to Marconi 6960B, Tektronix TDS794, Picoscope
      2000. Label wording in use: "FOR INDICATION ONLY — CALIBRATION
      NOT REQUIRED". REG-01 and QP-06 §8 updated to match.

- [~] **Anritsu MS2665C (BL-0013) — sent for UKAS calibration; in
      progress.** Dispatched to the cal lab; as at 2026-07-05 still being
      processed. On return, file the cert under `qms/records/calibration/`
      and update REG-01 BL-0013 (basis moves from "verification now; UKAS
      planned" to calibrated: cert no., date, expiry, cadence).

- [ ] **R&S SML 03 — request UKAS calibration quote.** Rohde &
      Schwarz UK (manufacturer service), Calibrate.co.uk, or Trescal
      UK. Confirm UKAS schedule covers signal-generator source
      calibration to 3.3 GHz. Native cal cycle is 3 years per R&S.
      Indicative UKAS cost: £400–£900 per cycle. Postal calibration
      is acceptable.

- [ ] **HP 8753ES — defer formal UKAS calibration.** Operate on the
      verification regime documented in
      `planning/equipment-inventory.md` and to be drafted into
      `/qms/procedures/` in Phase 3. If audit pushback on the
      verification approach ever arises, arrange on-site UKAS
      calibration at Bethnal Green (Keysight UK Services, Trescal UK,
      TMD Technologies, or NPL-affiliated specialist). Do not post
      the 8753ES — out-of-support status and the risk of damage to
      Type-N ports in transit make postal calibration economically
      unsound.

- [x] **Connector torque wrench — confirm presence and tagging.**
      Huber+Suhner SMA preset torque wrench, 1.0 N·m (type 74_Z-0-0-21),
      confirmed held. Listed in REG-01 as verification-only (preset
      break-type; annual function check). Tagged BL-0048 (sub-£200, so
      tracked in the QMS but not in Xero). Physical tag applied and first
      function check completed 2026-06-04 (functions correctly). Closed.

- [ ] **Anechoic chamber — confirm absence.** The two Ramsey shielded
      enclosures are RF-isolation enclosures rather than anechoic
      (RF-absorbing); confirm no other anechoic chamber is in use.

- [x] **HP 34401A multimeter (BL-0016) — re-calibrated and returned to
      scope.** Serial confirmed **3146A46647** on the unit's return
      (2026-07-13); the register typo (was `3146A46547`) is corrected.
      Re-calibrated by Niche RF Ltd (cert NRF24062026C, 2026-06-24, PASS
      50/50, next due 2027-06-24). BL-0016 moved from quarantine to the
      in-scope table in REG-01, 12-month cadence. Physically remove the
      "OUT OF CAL" label from the instrument.

- [x] **GPSDO asset tag.** BL-0047 (Leo Bodnar Precision GPS Reference
      Clock, no serial). Confirmed and recorded in REG-01 2026-06-03.

- [x] **Joulescope JS110 (BL-0008) — scope decided.** Out of scope.
      Used for indicative bench / development measurements only;
      labelled "FOR INDICATION ONLY — CALIBRATION NOT REQUIRED". If a
      future project requires Joulescope results in customer-facing
      records, the unit will be calibrated for that project under
      QP-06. REG-01 updated.

- [x] **Tekbox attenuator set (BL-0023, TBAS217173) — scope decided.**
      In scope. Used on customer projects (spectrum-analyser input
      protection, but the measurements feed customer-facing records).
      Verified in-house by S21 measurement on the VNA (BL-0029)
      against the SOL cal kit (BL-0024); chain valid to 7 GHz.
      Verification procedure and first record to be performed (open
      item below).

- [x] **Rigol MHO954 (BL-0033) factory cert.** No separate factory
      cal cert held on file; the manufacturer calibrated the
      instrument before sale (purchased new 2025-12-01) and the
      warranty runs to 2029-05-10. REG-01 records the position; an
      18-month in-house verification cadence applies in lieu of a
      formal cert.

- [x] **Tekbox TBMA4 traceability statement.** Closed — the batch
      test report received with the antenna is the manufacturer's
      published characterisation and no further traceability
      statement is available. REG-01 BL-0045 records the basis as
      manufacturer batch characterisation, accepted under clause
      7.1.5.2 for the use case.

- [ ] **Apply "FOR INDICATION ONLY — CALIBRATION NOT REQUIRED" label
      to BL-0008 (Joulescope JS110).** Add to the next round of
      labelling alongside any future moves.

- [ ] **First in-house verification of BL-0023 Tekbox attenuator
      set.** Perform after the SOL cal kit renewal returns from
      Kirkby. Measure S21 of each attenuator on the VNA (BL-0029)
      after user-cal against the renewed SOL kit. Record nominal
      value, measured value, deviation, pass/fail against the
      accepted tolerance per attenuator. File the verification record
      at `qms/records/calibration/tekbox-tbas217173-verification_<date>.md`
      and update REG-01 BL-0023.

- [ ] **Perform the first annual SOL cal kit verification (QP-18).** Due
      2026-06-27 (one year after the last external calibration, K1397
      2025-06-27); now due. Fix the QF-05 acceptance tolerances/frequencies
      first (item below), run per QP-18, file the record in
      `qms/records/calibration/sol-cal-kit-verification/`, and enter the
      result against BL-0024 in REG-01. The next external calibration is not
      due until 2027-06-27 under the 24-month interval (QP-06 §6.1). Kirkby
      Microwave was unable to perform a re-calibration in 2026 (illness); not
      required under the 24-month interval, but re-book early if the
      verification suggests any drift.

- [x] **QP-18 / QF-05 acceptance tolerances and spot frequencies set.** Done
      2026-07-13: ten spot frequencies (50 MHz–7 GHz) and the certificated S21
      of reference attenuator 0882 (from `attenuator-0882.s2p`, K1401) are
      pre-filled in QP-18 §6 and QF-05; acceptance tolerance ±0.30 dB on S21,
      set by the verification system's own measurement uncertainty (8753ES +
      85033 kit), not the certificate's. Reference s2p filed under
      `qms/records/calibration/`.

- [ ] **Substantiate the 24-month SOL cal kit interval.** Obtain the
      manufacturer's (Keysight/HP 85033) recommended calibration interval and
      assemble the kit's drift history across successive Kirkby certificates.
      Confirm or revise the 24-month external interval at the annual
      management review per QP-06 §6.1 (ILAC-G24 basis); interim control is
      the annual in-house verification under QP-18.

- [x] **Pemberton Digital asset tagging confirmed.** Pemberton
      equipment is asset-tagged under their own scheme (confirmed
      2026-06-03). The two companies' asset registers are distinct;
      REG-01 lists BLINKENLIGHT instruments only.

## New asset — BL-0051 (added 2026-07-05)

- [x] **Log BL-0051 in REG-01 (out-of-scope asset).** Done 2026-07-05 —
      REG-01 v1.1 adds BL-0051 (Dell PowerEdge R740XD, electromagnetic-
      simulation compute, serial CVJS6Z2) to the out-of-scope,
      non-measurement asset list. Not a measuring instrument; no
      calibration.
- [ ] **EM-simulation confidence (if used as design evidence).** If EM-solver
      results are ever cited as design-verification evidence (clause 8.3.4),
      add a short line to QP-15 on confidence in simulation (e.g. validation
      of solver results against measurement). Not required while results are
      design-exploration only.
- [ ] **Customer property on BL-0051 (QP-12).** If the server holds customer
      design packages/CAD for EM simulation, confirm that material is handled
      under QP-12 (identified, segregated, not committed to Git). Within the
      whole-organisation Cyber Essentials scope already.

## Calibration follow-ups (added 2026-06-02)

- [x] **SOL cal kit — renewal calibration scheduled.** Booked with
      Kirkby Microwave Ltd for the week of 2026-06-08; renewal will be
      complete before the current cert (K1397) expires on 2026-06-26.
      File the new cert under `qms/records/calibration/` and update
      REG-01 INS-05 on receipt.
- [x] **SOL cal kit (BL-0024) — returned uncalibrated; superseded by the
      24-month interval.** Kirkby could not complete the 2026 re-calibration
      (illness) and returned the kit uncalibrated. Under the 24-month external
      interval adopted 2026-07-12 (QP-06 §6.1), no external re-cal was due —
      cert K1397 (2025-06-27) remains the basis, next external cal 2027-06-27.
      The live action is the first annual in-house verification (QP-18) — see
      the open item above (due 2026-06-27). Closed 2026-07-13.
- [ ] **Kirkby Microwave — narrow traceability follow-up (option C).**
      Kirkby replied 2026-06-03 declining a UKAS-grade traceability
      statement: its reference standards receive a standard (non-UKAS)
      Keysight calibration — traceable to national standards but not
      accredited — so it cannot state expanded uncertainties. Follow-up
      to ask only for: the Keysight calibration certificate numbers and
      dates on Kirkby's reference standards, and a one-line written
      assertion that those standards are traceable to national
      standards. On reply, file alongside the cert at
      `/qms/records/calibration/` and update REG-01 §Notes and QP-06 §4
      with the documented (non-accredited) chain. Records the clause
      7.1.5.2 basis. Option B (UKAS calibration of the kit via Keysight
      UK, ~2× cost) deferred to a future renewal if a customer requires
      accredited uncertainties.
- [ ] **Controlled measurement band ceiling.** With the cal-kit cert at
      7 GHz (not 8 GHz), bound controlled S-parameter and amplitude
      measurements to ≤7 GHz, and explicitly state that measurements
      above 7 GHz (e.g. on INS-03 Anritsu MS2665C up to 21.2 GHz) are
      indicative-only and not used as controlled evidence. Reflect in
      QP-06 §4 and REG-01 INS-03 row. (Linked to the open question
      raised in the adversarial review on the traceability ceiling.)

## Shared-lab and competence setup (added 2026-05-21)

The QMS procedures (QM-02, QP-06, QP-12, REG-01) have been written as
if the items below are in place. They must actually be put in place,
within the next week or so, to match the documents.

- [x] **BLINKENLIGHT–Pemberton Digital co-occupation and
      confidentiality agreement.** Executed 2026-06-02 with supporting
      board and members' resolutions. Held at
      `qms/records/premises/co-occupation-agreement-blinkenlight-pemberton_2026-06-02.pdf`.
- [x] **Asset tags.** BLINKENLIGHT equipment is tagged with `BL-NNNN`
      tags aligned to the Xero fixed-assets register (confirmed
      2026-06-03; full inventory recorded in REG-01). Pemberton Digital
      equipment is tagged separately under their own scheme. GPSDO
      asset tag still to add — tracked separately above.
- [x] **Lockable storage for confidential items.** Lockable desk
      drawers in place 2026-06-03 (used in place of a separate safe).
      QM-02 and QP-12 updated.
- [x] **Shredder.** Purchased and en route 2026-06-03; in place this
      week for confidential paper waste (QP-12 §4).
- [x] **Add degree certificates and details.** BEng (Mechatronics
      Engineering, The University of Western Australia, 26 March 2014)
      filed at
      `qms/records/competence/degree-beng-mechatronics-uwa_2014-03-26.pdf`.
      BCompSci (Bachelor of Computer Science, Systems, The University of
      Western Australia, awarded 3 April 2014, combined degree with the
      BEng) filed at
      `qms/records/competence/degree-bcompsci-uwa_2014-04-03.pdf`. QP-10
      §3 updated for both.
  [ ] Purchase a NanoVNA (or repair existing) as a backup to the HP VNA

## Customer case study and InvenTree (added 2026-05-21)

- [ ] **Aalto export control classification (PO-AH000005952-2).**
      Determine and document the antenna's export control classification
      against Aalto's ECCD template (PR-FORM-007, in the engagement's
      `00-customer-property/`); file the completed classification in
      `06-handover/` and return to Aalto. Needed before shipment (target
      delivery 2026-07-13). Ref: Aalto engagement README handover section.

- [ ] **QP-15 §10 design worked examples.** Add the OWL v3.0 (Noktura)
      and an own-brand (Paradar/Bluespot) design engagement as worked
      examples under QP-15 §10 (DXComm §10.1 already in place). Confirm
      each is BLINKENLIGHT-invoiced; map to scope→design→prove→handover.

- [ ] **Aalto HAPS case-study permission.** Contact Chris at Aalto
      HAPS and request written permission to reference the
      relationship as a case study for the QMS and certification,
      maintaining confidentiality of programme details. Until granted,
      the end customer (Aalto HAPS / Airbus) is referenced in internal
      QMS documents only, not in auditor-facing or public material.
- [ ] **Review InvenTree stock-item ownership.** Check that every
      stock item is correctly owned by the 'Pemberton' or
      'BLINKENLIGHT' group (QP-16, QP-11).
- [ ] **Review InvenTree stock-location hierarchy.** Check that all
      stock locations sit under the correct top-level 'Pemberton' or
      'BLINKENLIGHT' Virtual Stock Location and are physically
      labelled accordingly (QP-16, QP-11).
- [ ] **Internal auditor ISO 9001 training.** Book Ian M onto the
      CQI/IRCA ISO 9001:2015 Foundation course (1 day, ~£375 +VAT,
      prerequisite) followed by the ISO 9001:2015 Internal Auditor
      course (2 days, ~£885 +VAT, CQI/IRCA certified) — the Internal
      Auditor course teaches audit method and is what clause 9.2
      competence needs; Foundation alone does not cover auditing.
      Together (~£1,260 +VAT, 3 days) they support CQI/IRCA Internal
      QMS Auditor registration. Hold his CV and both certificates in
      `/qms/records/internal-audit/` (QP-09 §2). Confirm his surname
      for the procedure. Provider option: QCS International (qcsl.co.uk).
- [ ] **Call Hiscox to extend insurance cover.** Add contents
      (equipment) insurance, non-cyber business-interruption cover, and
      personal-accident cover to the existing Professional Indemnity and
      Public/Products Liability policy. Cyber-event business interruption
      is already covered to £25,000 aggregate under the bundled Cyber
      Essentials policy (AIG via Sutcliffe & Co; `/qms/records/cyber-
      essentials/`), so the Hiscox extension is for the non-cyber gap in
      REG-02 R-08 (fire, theft, physical damage, equipment loss, no
      backup lab). File the updated Hiscox certificates in
      `/qms/records/insurance/` and update R-08 once in place.
- [ ] **Aviation products liability — bind the Chubb policy (quote
      NCQ30314).** Quoted 2026-07-15 via Castlemead (Adrian) with Marsh as
      scheme broker; underwriter Chubb European Group SE. Two options, both
      nil deductible, worldwide, £2M £4,063 + IPT and £5M £4,741 + IPT.
      Taking the £5M; £10M pricing requested as the marginal cost of limit
      is low. Note the limits are **aggregate**, and coverages A and B share
      one combined aggregate.

      Open before binding:
      - Quoted period runs 2026-07-20 to 2027-07-19 — inception has already
        passed. Get it re-dated or confirmed. Quote valid 60 days from
        2026-07-15 (to ~2026-09-13).
      - Queries sent to Adrian: (i) Key Facts sheet excludes unmanned
        aerial vehicles from Coverage B grounding cover, but the policy
        wording does not and its "Aircraft" definition expressly includes
        UAVs — confirm which governs; (ii) grounding cover requires a
        "Certified Aircraft" holding a type certificate, and the Aalto
        Zephyr holds only CAA Design Organisation Approval (July 2024) with
        a type certificate targeted late 2027 / early 2028 — so Coverage B
        may not respond to the Aalto exposure today; (iii) whether the
        AVN46B electrical and electromagnetic interference exclusion can be
        amended, this being the most plausible failure mode for an antenna
        supplier.
      - Rated on a declared annual sales value of £50,000, with a duty to
        notify increases. Confirm whether this means total turnover or
        aviation contract value before binding.
      - Quote is conditional on the products being **non-critical**. If a
        customer classifies a supplied item as flight- or safety-critical,
        the basis fails. Record the classification basis in the QMS.
      - Not covered, accepted for now: product recall and rectification
        (exclusions A.3 and A.6); design-error economic loss (A.4, see the
        Hiscox renewal item below); space and satellite work (A.7/A.8,
        Endorsement F not on the schedule); contractual liability beyond
        common law (General Exclusion 1).
      - Cover is occurrence-based, so it responds only if a policy is in
        force when an accident happens. Products already shipped go bare if
        the policy lapses. Budget as an indefinite annual cost.

      On binding: file the schedule, wording and Key Facts in
      `/qms/records/insurance/`, update `records/insurance/README.md`, and
      revise REG-02 R-08.

      **On binding — Aalto notification (closes the JP-AR-001 clause 12.3
      point).** Aalto's terms require product-liability cover far above
      that held (clause 12.3.4, USD 650M) but permit a lower figure agreed
      in writing by Aalto. At 2023 onboarding BLINKENLIGHT disclosed its
      cover and Aalto placed PO-AH000000188-1 with knowledge of it, but the
      PO's Specific Conditions are silent on insurance, so this is approval
      by conduct, not an express written variation (disclosure and approval
      record now filed at `/qms/records/customers/aalto-haps/`). When the
      Chubb certificate arrives, send it to Chris (or successor) with the
      good news and request his written confirmation that the insurance
      level is approved. File the reply in
      `/qms/records/customers/aalto-haps/` and note it in that README and in
      REG-02 R-09. This furnishes the certificate required under clause 12.3
      and converts approval-by-conduct into the written agreement clause
      12.3.4 contemplates.
- [x] **Hiscox PI / liability — policy recorded.** Done 2026-07-05.
      Single Hiscox policy PL-PSC10003370426/02, period 10/11/2025 to
      09/11/2026 (in date), next renewal **2026-11-09** (now on the QMS
      schedule); PI £1,000,000, public/products liability £5,000,000.
      `records/insurance/README.md` created and REG-02 R-08 updated (v1.1).
      Filename-year note captured in the README.
      - [ ] **Hiscox — correct registered address at renewal.** The public/
            products liability certificate still shows the former Poole
            registered office (Unit 13 Freeland Park, BH16 6FA); the company
            moved to Unit 309 The Pill Box on 19 October 2025. Ask Hiscox to
            reissue against the current address at the 2026-11-09 renewal.
      - [ ] **Hiscox — review PI limit and aviation exclusion at renewal
            (2026-11-09).** PI cover is currently £1,000,000 and excludes
            aviation work. Discussed with Adrian at Castlemead during the
            aviation products liability placement (July 2026): aviation-
            extended PI agreed as **not required immediately**, because the
            current Aalto work is manufacture to Aalto's own design and test
            plan, not design work by BLINKENLIGHT — so there is no live
            aviation design-liability exposure. **This holds only while that
            remains true.** If any aviation *design* engagement is taken on,
            aviation-extended PI must be in place first; treat it as a
            precondition of accepting such work, not a renewal-time item.

            At the 2026-11-09 renewal, replace the Hiscox policy with better
            cover: aviation-capable PI, and a limit review. Core revenue is
            design/R&D advice for aerospace/RF clients (Aalto/Airbus,
            DXComm/Commtrack), the exact exposure PI covers and where a
            negligent-design claim can exceed £1M. Check each client contract
            (and the canonical Terms of Business) for a stated PI minimum;
            consider raising to £2M. Public/products liability at £5M is
            adequate; no change. Market options researched in
            `planning/research/02-aviation-liability.md`. Note the Chubb
            aviation products policy does **not** fill this gap: exclusion
            A.4 removes loss from improper or inadequate design or
            specification, writing back only resulting injury or damage.
- [x] **Cyber Essentials renewal.** Completed 2026-05-22 (certificate
      7c7148de-…, profile 3.3 Danzell, whole-organisation scope; partner
      IASME, certification body World Computing). Held at
      `/qms/records/cyber-essentials/`. Recertification due 2027-05-22.
- [x] **First product test procedure(s).** Two issued under
      `qms/records/product-test-procedures/`: PTP-01 (DXComm Iridium
      Repeater, per-unit build test) and PTP-02 (Paradar 5 dBi whip,
      ISO 2859-1 batch acceptance, AQL 2.5%). Further lines (other
      Paradar/Bluespot products) added as they run under the QMS.
      The Paradar 5 dBi whip manufacturing spec v1.0 is done (filed at
      `qms/records/product-test-procedures/`). Remaining: set up the part
      in InvenTree per `planning/inventree-paradar-whip-setup.md`.

- [ ] **Paradar antenna — UK (UKCA) Declaration of Conformity.** The DoC
      on file (`records/product-compliance/`) is EU-framed (RoHS
      2011/65/EU, WEEE 2012/19/EU), dated 2021, with the former Poole
      address. For the UK market issue a current UKCA declaration citing
      the UK RoHS Regulations 2012 and UK WEEE Regulations with the
      present Unit 309 address; refile under `records/product-compliance/`.

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

## Shared facility — Pemberton Digital relationship

The lab at Unit 309 is shared with Pemberton Digital (a separate
entity under common control). Formalising the relationship discharges
parts of clauses 4.2 (interested parties), 7.1.3 (infrastructure),
7.1.5 (monitoring and measuring resources), and 8.5.3 (property
belonging to customers / external providers) in one set of documents.

- [x] **Co-occupation agreement BLINKENLIGHT → Pemberton Digital.**
      Drafted 2026-05-29 at
      `qms/records/premises/co-occupation-agreement-pemberton_2026.md`.
      Framed as a lightweight memorandum of understanding granting
      Pemberton a non-exclusive licence to occupy (not a tenancy/lease,
      to stay within the Workspace head-lease group-company sharing
      terms — head lease not referenced in the agreement itself).
      Establishes BLINKENLIGHT's primacy over the facility (clause
      7.1.3) and names Pemberton as a defined interested party (clause
      4.2). Common control stated openly. Rent £876.04/month + VAT,
      effective 17 April 2026, 14 days' notice either side. Workspace
      already notified of group-company occupation.
      Drafting complete: company number (14422623) and registered
      office filled; effective 17 April 2026 with the relationship
      recorded as running since Pemberton's October 2022 founding.
      Signatories settled — executed by Vytautas Rudys for BLINKENLIGHT
      and Andrew Cameron (the disinterested Pemberton director) for
      Pemberton. Patrick (director + significant shareholder of both)
      signs neither side. Note both BLINKENLIGHT directors are
      interested in the Agreement — Patrick via Pemberton directorship/
      shareholding, Vytautas via a ~3% Pemberton shareholding — so
      Vytautas is not fully disinterested; both declare their interest
      in the BLINKENLIGHT board minute. The agreement has no
      outstanding `TODO`s.
      Authorisation documents drafted (`qms/records/premises/`):
      - BLINKENLIGHT uses **unamended model articles**. Under Model
        Article 14 an interested director cannot count in the quorum/
        vote; with both directors interested and only two on the board,
        a members' written ordinary resolution under MA 14(3)(a) is
        required to disapply that restriction before the board can
        validly approve. Drafted as
        `members-resolution-blinkenlight_2026.md`, to be passed on or
        before the BLINKENLIGHT board meeting.
      - BLINKENLIGHT board minute and Pemberton board minute drafted.
        Pemberton's articles disapply Model Articles 13–14, so Patrick
        may declare-and-vote there; the Pemberton minute also records
        the SHA Schedule 6 Part 2 §7 Board Approval.
      - Sequence: members' resolution → both board meetings → sign the
        Agreement. Date each step on or before the next.
      Open follow-ups before/after signing:
      - [ ] **Pemberton Board Approval (connected-party transaction).**
            Confirmed against the actual SHA/Articles in
            `~/claude-workspace/pemberton-articles/` (the file first
            cited, `Pemberton Digital - Subscription Agreement.md`, is a
            customer template, not the SHA). The licence is a
            connected-party transaction (Patrick director/shareholder of
            both companies) caught by SHA Schedule 6 Part 2 §7 → requires
            **Board Approval**, NOT Investor/SFC consent (value ~£10.5k/yr
            is below the £25k capex/leasing threshold in Part 2 §4 and is
            not "indebtedness" under Part 1 §19). Action: minute a
            Pemberton board approval recording Patrick's declared interest
            (CA 2006 s.177/s.182; Articles 29.10 / 28.5), noting terms are
            arm's-length/market (~£876 + VAT), with Andy's concurrence.
            Patrick is NOT required to abstain (Model Articles 13–14
            disapplied), but the disinterested concurrence and the minute
            are the clean record. This board minute supersedes the
            informal "email Andy" plan as the proper governance record.
      - [ ] Sign and file the executed PDF in `qms/records/premises/`
            as `co-occupation-agreement-pemberton_<YYYY-MM-DD>.pdf`.
      - [ ] Confirm asset tags are physically applied to equipment
            before relying on clause 4.1 (auditor checks the bench).

- [ ] **Order asset tags for BLINKENLIGHT and Pemberton; tag all
      equipment.** Distinct tag series per entity so every instrument
      has an unambiguous owner. Underpins clause 7.1.5: each item in a
      calibrated measurement chain must have one named owner of
      calibration responsibility. Cross-reference tag IDs into the
      equipment inventory and calibration register. Source from a UK
      supplier (RS, Farnell, or a dedicated asset-label supplier such
      as Brady or Seton); combine with the "not in cal scope" label
      order above where practical.

- [ ] **Pemberton board resolution defining scope split.** Resolution
      recording that RF and antenna work sits with BLINKENLIGHT, plus
      the nature of the relationship, ensuring minimal overlap.
      Provides the documented basis for the clause 8.5.3 / confidentiality
      segregation answer (no overlapping RF work to compromise customer
      property), particularly for the unnamed HAPS aerospace programme.

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

## Preservation / ESD (added 2026-06-04)

- [ ] **Document ESD (electrostatic discharge) handling controls.**
      Surfaced while reviewing a client pitch deck that claims "ESD
      controls protect components during handling and testing". The
      practice is real — ESD-safe workbench plus handling routine — but
      nothing in the QMS documents it, so the claim is currently
      unsupported if a customer (or auditor) probes it. Draft a short
      preservation/handling procedure under clause 8.5.4 covering: the
      ESD-safe bench and its grounding, wrist-strap / handling routine,
      storage of ESD-sensitive parts, and any periodic check of the
      bench. Real, low-cost evidence for 8.5.4 — good clause to hold
      genuine practice against. Either a standalone QP or a section
      added to an existing preservation/handling procedure.

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
      Produces PDF snapshots of all controlled documents under `/qms/`
      at `main` HEAD into `/audit-pack/YYYY-MM-DD-<purpose>/` with
      metadata footers (ref, version, approval date, approver, commit
      hash). Pandoc + a simple frontmatter reader will do the job.
      Patrick can review the proposed script before it lands. Deferred
      to nearer the audit (adversarial-review-findings.md A3).

## Pre-v1.0 sweep follow-ups (added 2026-06-03)

These items emerged from the adversarial review discussion and are
captured here so they survive the repo restructure. See
`adversarial-review-findings.md` for the full tracker.

- [x] **Pre-v1.0 text-only sweep.** Completed 2026-06-03 before the
      QMS v1.0 single-commit. Closed: broken cross-references in QP-06
      and QP-15; the "Salable and built" trigger wording in QP-11 and
      QM-01; build-completion gating qualified; QP-17 §3/§4 rating
      contradiction; QP-03 §3 clause mapping; QP-07/QP-08 title fixes;
      QP-10 OWL disambiguation; QM-01 §10 and REG-02 R-01/O-02 escrow
      naming standardised on techUK; QP-13 §5 phantom log routed to
      REG-03; QP-15 §4 added clause 8.3.3(d) consequences-of-failure;
      QP-15 §6 added explicit 8.3.4(a) results-to-be-achieved and
      8.3.4(e) actions-on-problems mapping; MTI Technology added to
      REG-02 R-07 and QM-02 §4.

- [ ] **Reference the 2024 Aalto HAPS engagement as historical
      context.** Add a paragraph to QP-15 §10 (Worked examples)
      describing the prior 2024 Aalto HAPS engagement as historical
      evidence of capability for this customer type and product class.
      State clearly that the engagement predates QMS go-live
      (2026-05-21); records are held in pre-QMS files (Patrick's
      working folders, email, spreadsheets); no claim of QMS-control
      over those records. Also cite the 2024 engagement in QP-10 §3 as
      experience-based competence evidence for aerospace antenna work.
      Patrick to provide the PO reference and a one-paragraph
      description.

- [ ] **REG-04 CPD backfill 2023–2025 with personal projects.**
      Clause 7.2 accepts experience-based competence development;
      open-source design work with public commit history is genuine,
      verifiable evidence. Add entries to REG-04 covering:
      - `power-rail-probe` (github.com/blinken/power-rail-probe) —
        precision low-noise instrument design, BLINKENLIGHT's bulk
        personal research project; RF and measurement, PCB, embedded
        competence.
      - `OpenWeedLocator` (github.com/geezacoleman/OpenWeedLocator)
        collaboration — mixed-signal precision-agriculture platform;
        PCB, embedded and integration competence. The OWL v3.0
        redesign for Noktura sits under this.
      - `pcb-checklist` (github.com/blinken/pcb-checklist) —
        knowledge consolidation; PCB design discipline.
      Patrick to confirm the year of each activity. Plus any standards
      reading, KiCad/Sonnet upgrades tracked, or vendor/tool training
      attended. Draft the REG-04 entries from this when years are
      confirmed.

- [ ] **Issue an associate competence record / matrix template.**
      QP-10 §5/§7 references a record under `/qms/records/competence/`
      that does not exist. Draft a stub matrix template (associate,
      areas of competence, evidence reviewed, assessment outcome,
      date, reviewer) with a row marked "no associate currently
      engaged" so the procedure is operable. File at
      `qms/records/competence/associate-competence-matrix.md`.

- [ ] **Issue a principal competence record / summary.**
      Pull together the principal's competence evidence (BEng UWA,
      BCompSci pending, amateur radio licence M7BLK, shipped own-brand
      products power-rail probe and Paradar OWL boards, Aalto HAPS
      programme experience, CPD pointer to REG-04) as a one-page
      record under `/qms/records/competence/`. References the existing
      evidence files.

## Supplier certificates outstanding

- [ ] **Wye Valley Services Ltd — QMS certificate.**
      Renewed certificate received and filed 2026-07-21
      (`wye-valley-services-iso9001-as9100d-cert-20224752_2026-07-05.pdf`):
      a single ISO 9001:2015 certificate incorporating AS/EN 9100 Rev D
      (AS9100D), issued by Quality Systems Certifications Ltd (QSC Ltd),
      cert 20224752, scope Precision Engineering excluding clause 8.3,
      current 2026-07-05 and expiring 2027-07-04. The lapse of the
      previous certificate is closed: renewal is effective the day
      after the previous expiry, so cover was continuous. REG-05 §1 and
      §2 updated (v1.7); the superseded certificate is retained in
      `suppliers/` under QP-01 §10. The InvenTree company record was
      updated and the renewed certificate uploaded on 2026-07-21, so
      the live approval status at point of use (QP-16 §4) matches
      REG-05. One open point:
      - **QSC Ltd accreditation — closed as not material to
        certification; one narrower point left open.** The certificate
        carries no accreditation mark and no UKAS-accredited body of
        that name was found, so treat it as non-accredited. This is
        not a nonconformity: AS9100D 8.4.1 NOTE makes certification-body
        data a permitted input to supplier evaluation, only one element
        of it, and leaves BLINKENLIGHT responsible for verifying
        conformity regardless. Approval rests on manufacture to
        BLINKENLIGHT drawings with incoming inspection, which is
        unaffected. REG-05 makes no accreditation claim for this
        supplier and needs no correction.
        Open: for AS9100/EN 9100, industry recognition requires a
        certification body accredited under EN 9104 and listed in the
        IAQG OASIS database. Check certificate 20224752 in OASIS, or
        ask Wye Valley which body accredits QSC Ltd. Until confirmed,
        do not cite Wye Valley's AS9100D status to Aalto or any other
        aerospace customer as evidence of sub-tier aerospace
        certification; cite the drawing-conformity and incoming-
        inspection controls instead.

## Active engagement follow-ups

- [x] **Aalto PO-AH000006085-1 — quantity and connector decision.**
      Resolved 2026-07-20. No connector substitution will be made. Build
      proceeds only to the quantity supportable from the existing stock of
      the drawing-specified connector C-1050770 (TE 1050770-1); the balance
      of PO-AH000006085-1 is held pending an updated drawing issue carrying
      the replacement connector part number. Aalto has the change under
      their own change control. No deviation from the approved design
      package arises, and no concession is required.
      Consequence: the PO will be satisfied across two drawing issues.
      Units built to each issue are separate configurations and must be
      recorded, serialised and certified separately (see the InvenTree
      part-revision handling in the Certificate of Conformity work).

- [ ] **NCAGE application — submitted 2026-07-21, awaiting approval.** NATO
      Commercial and Government Entity code applied for through the UK National
      Codification Bureau (ncb.mod.uk) for BLINKENLIGHT Ltd at Unit 309.
      Requested as Manufacturer. Record the Reference string used on the
      application here — it must be re-entered to confirm the creation and is
      the only link back to the request. On issue: add the code to the
      Certificate of Conformity issuer block (marked in
      `planning/inventree/certificate-of-conformity.html`), satisfying Airbus
      A1505 §3.2.1(b)(iii), and record it in CLAUDE.md company facts.
      Note the registry entry is public: it carries the business telephone,
      info@ address and the GLN.

- [ ] **Update the GS1 UK record to BLINKENLIGHT Ltd.** The annual licence
      (company prefix 506088907, GLN 5060889070001) is issued to "Paradar" —
      a product brand, not the legal entity — with superseded contact details.
      The prefix is the documented basis of the GTIN scheme under QP-11, so
      the licensee should be the legal entity at the current registered
      address. Filed at
      `qms/records/product-compliance/gs1-uk-licence-expires_2026-12-27.pdf`.
      Undertaken 2026-07-21 on the basis that the GLN was submitted to the
      NCAGE (NATO Commercial and Government Entity) registration the same day;
      until GS1 is corrected, a public NATO registry entry for BLINKENLIGHT
      Ltd cites a GLN registered to a differently-named licensee.
      Replace the filed certificate once reissued.

- [ ] **GS1 UK licence renewal — due 2026-12-27.** Annual. Lapse invalidates
      the company prefix and with it the basis of the GTIN product numbering
      under QP-11. Track alongside the other expiries (insurance, Cyber
      Essentials, supplier certificates).

- [ ] **Extract Aalto's flow-down requirements into a checklist mapped to QMS
      procedures.** Aalto's supplier terms are held only in the PO PDFs under
      `00-customer-property/`. Nothing in the tracked record establishes what
      they actually bind BLINKENLIGHT to — whether AS9102 first article
      inspection, counterfeit-part controls, workmanship standards, record
      retention or a mandated Certificate of Conformity (CoC) format apply.
      Read the terms clause by clause against the QMS and record the mapping.
      This governs over the generic Airbus requirements researched in
      `planning/research/03-aerospace-coc-requirements.md` and blocks sensible
      decisions on what to volunteer in the documentation pack.

- [ ] **Define a controlled list of authorised signatories.** Aerospace
      customers expect release certificates to be signed by a named authority
      drawn from a controlled document (see the CAV Systems comparator in
      `planning/research/03-aerospace-coc-requirements.md` §4). Currently the
      CoC hard-codes Patrick Coleman, Technical Director, with no controlling
      record. Cheap to add — likely a short register or a section of QP-03
      (roles and responsibilities) — and commonly missed by small suppliers.

- [x] **Rework the QMS record retention clause (QP-01 §10).** Done 2026-07-21.
      Period set at fifteen years from creation of the record, with the
      airworthiness carve-out (operational life, or transfer to the customer),
      a hold on disposal pending a claim, investigation or audit, and
      precedence for QP-12 (customer property) and UK GDPR storage limitation.
      The period is now stated **only** in QP-01 §10; the twenty-two other
      documents that previously restated "six years" reference the clause
      instead. Basis recorded in
      `planning/research/03-aerospace-coc-requirements.md` §6.

- [ ] **File Aalto's acceptance of partial delivery (PO-AH000006085-1).**
      The engagement README now records that Aalto accepted delivery in two
      tranches and that the connector change is under their change control.
      The supporting correspondence must be filed in the engagement's
      `01-scope/` — it is the evidence for splitting a PO quantity and for
      the second tranche's revised date. Correct the resolution date in the
      README if Aalto's acceptance predates 2026-07-20.

- [ ] **CA-2026-001 — complete root-cause analysis and corrective action
      (late delivery, PO-AH000005952-2).** Raised 2026-07-13 in REG-03 for
      missing the contractual PO delivery date (2026-07-16; revised estimate
      ~2026-07-24, ~8 days late). Determine the root cause (why build/test/
      documentation ran beyond the PO date), decide corrective action — or
      justify none if a genuine one-off — confirm Aalto's acceptance of the
      revised date, and close the entry (QP-14). Reviewed at management
      review (QP-07).
      Do not proceed to build until resolved (hold beyond detail-part
      procurement). On reply, close the README open points.

- [ ] **Set up connector parts in InvenTree.** Create the internal part and
      supplier/manufacturer parts for C-1050770 (TE Connectivity 1050770-1,
      obsolete). Also enter the original circa-2023 purchase order for the
      9 off obsolete connectors (bought by BLINKENLIGHT against a future
      order, pre-InvenTree) so the existing stock has an InvenTree
      provenance/traceability record — this is now the stock the first
      tranche of PO-AH000006085-1 is built from, so its traceability is
      load-bearing for the Certificate of Conformity.
      The replacement connector is not set up until Aalto issue the updated
      drawing naming the part they have selected.

## Repository restructure (2026-06-03)

- [ ] **QMS submodule surgery.** Decision: `qms/` to be split into its
      own git repository, added back to the parent as a submodule so
      top-level `git status` retains visibility. See
      `planning/repo-structure-plan.md` for the implementation. Run
      after this sweep and after Patrick creates the empty private
      GitHub repository.

# Walkthrough: running the Aalto HAPS PO through the QMS

A practical, step-by-step reference for the first real engagement run
through the BLINKENLIGHT ISO 9001:2015 QMS. Customer: Aalto HAPS
(Airbus). Customer PO: **PO-AH000005952-2**. Engagement reference:
`aalto-haps-PO-AH000005952-2`. Manufacture-to-existing-design of
antennas to an Aalto-supplied test plan.

This file lives in `/planning/` and is not part of the controlled QMS.
It is intended as Patrick's working reference while operating the QMS
in production mode for the first time. Keep it open in another tab as
you go.

## Pre-launch checklist (close before the first controlled measurement)

- [x] Engagement folder structure created at
      `qms/records/engagements/aalto-haps-PO-AH000005952-2/` with the
      eight subfolders and a README.
- [x] Reusable engagement template at `qms/templates/engagement/`
      (copy when starting any future engagement).
- [x] InvenTree serialisation scheme set to `YYYYWWNN` and recorded in
      QP-11 §5.
- [x] "For indication only — calibration not required" labels applied
      to out-of-scope instruments (Marconi 6960B, Tek TDS794, Picoscope
      2000).
- [x] SOL cal kit renewal booked with Kirkby for the week of
      2026-06-08 (current cert K1397 expires 2026-06-26).
- [x] Cyber Essentials current to 2027-05-22.
- [x] Lockable desk drawers in place for confidential items.
- [x] Shredder en route.
- [x] Co-occupation agreement with Pemberton Digital executed
      2026-06-02.
- [x] Standing approved distributors confirmed in InvenTree: RS, Mouser,
      Digi-Key, Farnell, Accu (Accu holds UKAS-accredited ISO 9001).
- [x] Controlled measurements bounded to ≤ 7 GHz (in QP-06 and REG-01).
- [ ] Asset tags ordered; applied 2026-06-04 to in-scope BLINKENLIGHT
      instruments and to the out-of-scope set.
- [ ] Git commit signing + branch protection enabled before this
      engagement's records are committed.
- [ ] Part Test Template configured in InvenTree against Aalto's test
      plan (do this once the test plan arrives and the part is loaded).

## Stage 0 — PO arrives

When Chris's email lands:

1. Note the engagement reference: the folder already exists at
   `qms/records/engagements/aalto-haps-PO-AH000005952-2/`.
2. Save the PO PDF to `04-purchasing/aalto-PO-AH000005952-2.pdf`.
3. Save the test plan to:
   - `02-build-package/aalto-test-plan-<version>.pdf` (the acceptance
     basis — what we are testing against)
   - `00-customer-property/aalto-test-plan-<version>.pdf` (as customer
     property — held under QP-12)
4. Save any drawings or other Aalto-supplied IP to
   `00-customer-property/` with dates noted.
5. Update the engagement `README.md`: customer-property received,
   list with file names and dates.

A short note inline in the README, for example:

> Customer property received 2026-06-03 from Chris (Aalto HAPS):
> - test plan v1.2 (Aalto-confidential) — held in `00-customer-property/`
> - antenna assembly drawings Rev C (Aalto-confidential) — held in
>   `00-customer-property/`
> Held under QP-12; segregated; access limited to the engagement; not
> disclosed publicly without Aalto's permission.

## Stage 1 — Scope and acceptance (QP-15 §3)

Copy the scope template:

```bash
cp qms/templates/engagement/01-scope/scope-template.md \
   qms/records/engagements/aalto-haps-PO-AH000005952-2/01-scope/scope-aalto-haps-PO-AH000005952-2.md
```

Fill it in. The key fields specific to this engagement:

- **Contract in force:** Aalto HAPS supplier terms (BLINKENLIGHT
  onboarded). BLINKENLIGHT Terms of Business v2.1 do not apply.
  Anything contractual — IP, payment, warranty, delivery, acceptance,
  liability — is governed by Aalto's terms; cite the specific clauses
  the engagement relies on.
- **Confidentiality:** Aalto HAPS NDA in force; reference the NDA file
  and date.
- **Inputs:** Aalto's test plan as the success-test definition and
  acceptance criterion; the antenna's compliance basis (RED/UKCA
  position from the prior design file, if any); the Aalto drawings.
- **Assumptions:** design is existing (no new design work); all test
  points at or below 7 GHz (confirm from the test plan against the
  controlled-measurement ceiling in QP-06 §4); in-house manufacture
  and test; standing supplier list adequate.
- **Out of scope:** any test or measurement above 7 GHz; new
  characterisation; long-term maintenance.
- **Plan:** lead-time bound by the longest-lead component (typically
  the antenna substrate and any specialist connector); cycle is
  scope → purchase → build → test → handover.
- **Acceptance:** at the bottom, sign your own approval date and note
  the customer acknowledgement reference (Chris's confirmation email).

Email Chris with acceptance and the target delivery date once you have
the lead-time view (after the BOM check in Stage 2).

> Hi Chris,
>
> Acknowledged: PO-AH000005952-2 for [N] off [part], to test plan
> v[X]. Filed under our ISO 9001 QMS as engagement
> aalto-haps-PO-AH000005952-2; your test plan, drawings and PO are
> held as customer property under our customer-property procedure.
>
> Lead-time check in progress against our standing distributors. Will
> confirm target delivery date by end of week — first-pass estimate
> is [N] weeks subject to PCB and any specialist component lead time.
>
> Our standard verification regime applies: all controlled
> measurements at or below 7 GHz against the cal-kit traceable
> reference (Kirkby cert K1397).
>
> Aalto supplier T&Cs govern.
>
> Best,
> Patrick

Save the sent email (or a note of it) to `01-scope/` with the date.

## Stage 2 — Purchasing and goods-in (QP-16, QP-13)

In **InvenTree**:

1. **Project code**: tag every PO, build order and sales order
   `BLINKENLIGHT-aalto-haps-PO-AH000005952-2`. This keeps the work
   searchable, segregated from Pemberton, and tagged to one engagement.

2. **Bill of materials** check: pull the antenna's BOM (existing
   product file). For each line, identify the standing approved
   distributor — RS, Mouser, Digi-Key, Farnell, or Accu — and check
   stock and lead time.

3. **Raise the purchase orders** in InvenTree, one per supplier. Each
   PO line carries:
   - Supplier and supplier part number (links to the supplier-part
     record).
   - Quantity, unit price, target receipt date.
   - Any compliance flag the spec demands (RoHS, REACH, declaration
     required).
   - For Accu: the part-level certificate of conformity is requested
     as a matter of standard practice given their QMS posture.

4. **Place the orders**.

5. **On goods receipt**, for every line received:

   - In InvenTree, **receive against the PO line**. This creates the
     stock items and posts them to the receiving location.
   - For each item:
     - Bag the item.
     - Print the InvenTree stock label and stick it on.
     - Capture the batch or lot number from the supplier's
       packing/label into the stock item. Capture serial numbers
       where the item has one or where its value is >£50 (per
       QP-11 §5).
   - **Goods-in check** against the PO: correct part, correct
     quantity, visible damage, any required documentation/certs
     present. Pass → stock item available for build. Fail → set the
     stock item to a rejected/quarantined status in InvenTree, move
     to the quarantine stock location, and:
     - Record what failed in the engagement folder
       (`04-purchasing/goods-in-issues.md`) — one line per failed
       receipt, dated.
     - **If this is a real supplier failure** (wrong part, late
       beyond the agreed date, damaged), **open a REG-03 entry** at
       `qms/records/capa-log.md`. This is the right way to seed the
       corrective-action log: with real events, not invented ones.
       Format follows QP-14 §6 (CA-2026-NNN identifier).
   - **Scan the stock item into its final storage location** under
     the `BLINKENLIGHT` Virtual Stock Location.

6. **Subcontracted fabrication (if any)**: if antenna substrate or PCB
   is sub-contracted, raise the PO with the design package and revision
   in the purchasing information. On receipt, verification is by
   inspection and bench measurement against the supplied spec, with
   nonconforming items handled under QP-13.

7. **Update the engagement README**: list the InvenTree PO numbers in
   `04-purchasing/` with a one-line index per PO.

## Stage 3 — Build and test (QP-11 §5.1, QP-06, QP-15 §6)

### Before the first unit

1. **Confirm the antenna part is marked `trackable` and `Salable`** in
   InvenTree. Trackable so each unit gets a serial number (scheme
   YYYYWWNN); Salable so it is in scope of Quality Objective 2.

2. **Configure the Part Test Template** against Aalto's test plan.
   For each test in Aalto's plan, add a test on the InvenTree part:

   | Field | Set to |
   |---|---|
   | Test name | Exact wording from Aalto's plan |
   | Required | true (must pass before the build output can be completed) |
   | Requires value | true if a measured value is part of the plan (return loss in dB, gain in dBi, etc.) |
   | Requires attachment | true where Aalto wants the raw capture retained (typically yes for S-parameter sweeps and spectrum captures) |

3. **Write a short product test procedure** for this antenna — the
   "acceptance limits, setup, instrument used" addendum that sits
   alongside the templates (per QP-11 §5.1). Store at
   `05-build-and-test/test-procedure-<antenna>.md`. Reference the
   Aalto test plan it derives from; record:
   - Which REG-01 instrument is used for each test, by asset tag.
   - Cable/adapter chain used (with the cable register entries).
   - VNA user-cal step against the SOL kit, and the cert number to
     cite (K1397 until 26 June, then the renewed cert).
   - GPSDO lock check before every measurement (per QP-06 §5.1).

4. **Confirm the instrument state** that will be used:

   - VNA HP 8753ES, asset tag `BLK-INS-01`
   - GPSDO Leo Bodnar, asset tag `BLK-INS-04`
   - SOL cal kit, asset tag `BLK-INS-05`, cert K1397
   - Signal generator R&S SML 03, asset tag `BLK-INS-02` (if used)
   - Spectrum analyser Anritsu MS2665C, asset tag `BLK-INS-03`
     (controlled at ≤ 7 GHz only)

### For each unit built

1. **Raise a Build Order** against the antenna part for the quantity
   to build (typically the whole batch). InvenTree allocates serial
   numbers per the YYYYWWNN scheme. For example, the first batch in
   ISO week 23 of 2026: serials `20262300`, `20262301`, ...

2. **Assemble** the unit per the build procedure / drawing.

3. **Test the unit** against the Part Test Template:
   - **Confirm GPSDO lock** — both LEDs solid red. Record in the
     test result notes.
   - **User-cal the VNA** against the SOL kit with the actual cable
     and adapter chain. Save the user-cal data. The cal-kit cert
     number (K1397) goes into the test result notes.
   - **Run each test** in the Part Test Template:
     - Decide pass/fail against the Aalto criterion.
     - Enter the measured value.
     - Attach the raw capture (S-parameter `.s1p`, spectrum capture
       `.png`/`.csv`) to the StockItemTestResult.
     - In the notes, record the calibrated instrument's asset tag
       (e.g. `BLK-INS-01`).

4. **InvenTree gates the Build Order completion** on all required
   tests passing. All passed → Build Order completes; the serialised
   stock item is a finished good in the `BLINKENLIGHT` Virtual Stock
   Location. One failed → stock item to rejected/quarantined status,
   moved to the quarantine location. Investigate:
   - If rework brings it within spec, re-test, re-record, complete.
   - If scrap, raise a CAPA entry in REG-03 if the failure indicates
     a process issue (not a one-off component variation), and a
     QP-13 disposition note in `05-build-and-test/`.

### Example test result (what an auditor sees)

```
Serial:        20262300
Part:          ANT-AALTO-HAPS-XBAND-RX (Rev C)
Build order:   BO-20262300
Test:          Return loss S11 at 5.8 GHz
Required:      Yes
Result:        Pass
Measured value: -18.4 dB (target ≤ -15 dB)
Notes:         Measured on HP 8753ES (BLK-INS-01), user-cal against
               Kirkby 85033 cal kit (BLK-INS-05) cert K1397.
               GPSDO BLK-INS-04 locked (both LEDs solid red).
               Cable chain: SMA semi-rigid C-01 + N-SMA adapter A-03.
Attachment:    20262300-S11.s1p
Date:          2026-06-15 11:42 BST
User:          pcoleman
```

In the engagement folder under `05-build-and-test/`:

- The product test procedure (above).
- A `build-test-index.md` listing each serial with a one-line summary
  (date, pass/fail, link or reference to the InvenTree record).
- For any failed-then-passed unit, a short note of what happened.

## Stage 4 — Handover and shipment (QP-15 §7.1, QP-11 §5)

For the batch:

1. **Generate the per-serial test report** (Google Doc → printed +
   exported to PDF per QP-11 §5). One page per serial; print the
   single page for each unit and put it in that unit's box.

2. **Draft the Statement of Conformity** from
   `qms/templates/engagement/06-handover/statement-of-conformity-template.md`.
   Save filled-in version as
   `06-handover/statement-of-conformity_<YYYY-MM-DD>.pdf` (export to
   PDF and sign before sending).

3. **Draft the Delivery Note** from
   `qms/templates/engagement/06-handover/delivery-note-template.md`.
   Save as
   `06-handover/delivery-note_<YYYY-MM-DD>.pdf`.

4. **InvenTree sales/dispatch**:
   - Allocate the serialised stock items to a sales order for the
     batch.
   - Mark them dispatched against the courier consignment reference.
   - Record the dispatch date.

5. **If the agreed delivery date slipped** at any point, the at-risk
   notification email to Chris must have been sent **before** the
   originally agreed date (per Quality Objective 4). Save that email
   to `06-handover/at-risk-notification_<YYYY-MM-DD>.eml` (or as a
   `.md` note of what was said and when).

6. **Update the engagement README** Status to `Delivered`, fill in
   `Actual delivery date`, link to the handover artefacts.

## Stage 5 — Post-engagement (QP-17, QP-07)

Within two weeks of delivery:

1. **Customer satisfaction debrief with Chris**. Use the template at
   `qms/templates/engagement/07-customer-satisfaction/debrief-template.md`.
   Conduct over a 15-minute call or by email. Capture answers in
   the customer's own words. Save at
   `07-customer-satisfaction/debrief_<YYYY-MM-DD>.md`.

2. **Any negative feedback** raises a CAPA entry in REG-03 per
   QP-17 §5.

3. **Close-out paragraph** in the engagement README — summarise: PO
   to delivery in N weeks, M units delivered all-pass (or the
   breakdown), customer rating, anything Aalto called out as
   improvable. This becomes management-review input under QP-07.

4. **Mark Status: Closed** in the engagement README.

## What this engagement produces for the QMS

By the end you will have generated, naturally, all of the following —
which were Major audit risks because none of them existed before:

- One fully evidenced engagement under `qms/records/engagements/`,
  end-to-end (the worked example QP-15 §10 has been calling for).
- One configured Part Test Template, with a real product test
  procedure.
- Real per-unit test results (StockItemTestResult records) with
  attached measurement files and asset-tag traceability — the
  evidence behind Quality Objective 2.
- A populated REG-03 CAPA log (assuming at least one supplier
  hiccup, late milestone, or test re-run during the engagement).
- The first customer-satisfaction record — evidence behind
  Quality Objective 5 and QP-17.
- One signed Statement of Conformity and one batch delivery note
  with serials — the QP-15 §7.1 handover-pack evidence.
- A live management-review input for the next QP-07 cycle.

Running this engagement is exactly the path from "QMS exists" to
"QMS demonstrably operates."

## Quick reference — records and where they live

| Artefact | Folder | InvenTree |
|---|---|---|
| Customer PO | `04-purchasing/aalto-PO-AH000005952-2.pdf` | — |
| Aalto test plan | `02-build-package/`, `00-customer-property/` | — |
| Aalto drawings | `00-customer-property/` | — |
| Scope | `01-scope/scope-<ref>.md` | — |
| BLINKENLIGHT POs to suppliers | `04-purchasing/` (one-line index); the records themselves | InvenTree PO numbers |
| Goods-in records | `04-purchasing/goods-in-issues.md` for failures | Stock items, batch/serial on receipt |
| Build orders | `05-build-and-test/build-test-index.md` (one-line index) | InvenTree Build Orders |
| Test procedure (per product) | `05-build-and-test/test-procedure-<antenna>.md` | Part Test Template configured against this |
| Test results (per serial) | — | StockItemTestResult on each serialised stock item, with attachments |
| Statement of Conformity | `06-handover/statement-of-conformity_<date>.pdf` | — |
| Delivery note | `06-handover/delivery-note_<date>.pdf` | — |
| Sales order / dispatch | `06-handover/` (references) | InvenTree sales order |
| Customer-satisfaction debrief | `07-customer-satisfaction/debrief_<date>.md` | — |
| Corrective actions raised | `qms/records/capa-log.md` (REG-03) | — |

## Common questions

**Do I serialise the imported Paradar/Bluespot antennas in InvenTree?**
No — they're batch-tracked per QP-11 §5.2. The Aalto antennas are
in-house build, so they're per-unit serialised under §5.1. The two
flows coexist in InvenTree.

**What if Aalto's test plan has a test point above 7 GHz?**
Pause the engagement. Either Aalto agrees the test is informative-only
(and not a release gate), or we extend the cal regime before the
test (out-of-scope for this engagement under the current QMS). Confirm
with Chris in writing whichever path is taken.

**What if a build fails goods-in and there's no alternative supplier?**
Raise a REG-03 entry; reply to Chris with an at-risk notification
**before** the next milestone date; document the recovery plan in the
engagement README. This is exactly the on-time-delivery objective at
work.

**What if the cal kit cert expires mid-engagement?**
The kit is currently valid to 2026-06-26 and the renewal is scheduled
the week of 2026-06-08. If for any reason a controlled measurement
needs to happen between 26 June and the new cert returning, the
controlled measurements are paused; informal characterisation can
continue but isn't QMS-traceable until the new cert is in hand.

**Do I update QM-01 §6 metrics live during the engagement?**
No — the metrics are reviewed at the annual management review (QP-07).
Records accumulate naturally; they are tallied at review time.

**What does "audit-defensible" actually mean for this engagement?**
You can show the auditor: the scope, the customer property handling,
the InvenTree POs raised against approved suppliers, the goods-in
records, the configured Part Test Template, the per-serial pass/fail
results with raw captures and instrument asset tags traced to REG-01,
the Statement of Conformity and delivery note in the handover pack,
the customer-satisfaction debrief, and any CAPA raised. End to end,
real, dated. That is the operating evidence Stage 2 looks for.

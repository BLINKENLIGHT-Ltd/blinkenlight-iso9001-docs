# Adversarial review — findings tracker

Canonical list of findings from the adversarial compliance read-through
of 2026-05-28 (nine Opus agents, read-only, prioritised issue lists
returned). Status is updated as findings are addressed.

Legend: **Done** = resolved on disk; **In flight** = will resolve as
the Aalto engagement (or another live process) populates it; **Open**
= still requires explicit action; **Deferred** = intentionally parked
with a return date.

## Group A — controls overstated as operating

| # | Finding | Status | Note |
|---|---|---|---|
| A1 | QP-01 §6 commits unsigned, approval claim fails today; enable signing + branch protection on `main` | **Done** | Commit signing enabled and tested 2026-06-03; QP-01 §6 TODO removed. |
| A2 | QP-01 §9 overclaimed "two remotes" | **Done** | Rewritten honestly: GitHub primary + local working copy + quarterly encrypted off-site HDD; no second mirror required. |
| A3 | QP-01 §11 Audit Pack render script missing; `/qms/tools/` empty | **Deferred** | Decision 2026-06-03 (Patrick): defer until actual audit. Build the script then; not essential for launch. The fallback (read-only collaborator seat to /qms/) covers the auditor route in the meantime. |
| A4 | `/qms/README.md` stale and self-contradictory | **Done** | Rewritten as a navigation aid for the populated tree. |
| A5 | QM-02 / QP-12 physical controls (safe, asset tags, shredder, lab-sharing agreement) overstated as in-place | **Done** | Co-occupation agreement executed 2026-06-02; lockable desk drawers (BL-0046) in place; shredder en route; BLINKENLIGHT and Pemberton asset tags applied. Reality matches the docs. |
| A6 | QP-15 no engagement records; QF-01 missing; worked-examples are TODO placeholders | **In flight** | Aalto engagement folder (`aalto-haps-PO-AH000005952-2/`) created; will produce the first end-to-end evidence as it runs. QF-01 to be issued during the first formal design review. Open: whether to also document the previous 2024 Aalto engagement as historical reference (Patrick to decide; see notes below). |
| A7 | QP-09 "lead auditor" overstated for Ian (Internal Auditor-trained PM); "before or soon after" too loose | **Open** | Wording fix: change "lead auditor" → "internal auditor" in QP-09 / QP-03 / QM-01; tighten "before or soon after" → strictly before the first audit. Independent of the training decision itself, which is parked under "Decide later". |
| A8 | REG-03 corrective-action log empty | **In flight** | Aalto engagement will produce the first real entries naturally (supplier hiccups, test re-runs, at-risk milestone notifications). Pre-Stage-2 seeding with 4–8 historical events still wanted if real ones don't accumulate. |
| A9 | REG-04 stale single 2022 entry | **Partial** | Degree certificate filed for context. Backfill of 2023–2025 CPD still to do; Patrick proposes using personal open-source design projects (power-rail-probe, OWL, pcb-checklist) as experience-based CPD — accepted under clause 7.2 "education, training, or experience". To be drafted into REG-04. |
| A10 | QP-10 §5/§7 associate competence record/matrix doesn't exist; principal evidence directory mostly empty | **Partial** | BEng cert filed. Still to do: (a) issue an empty associate competence matrix template under `/qms/records/competence/`; (b) record principal competence summary as a separate record. Both are quick drafts that can be done from existing information. |

## Group B — clause-level gaps

| # | Finding | Status | Note |
|---|---|---|---|
| B1 | QP-06 traceability ceiling vs MS2665C in-scope range | **Done** | Controlled measurements bounded to ≤ 7 GHz in QP-06 §4 and REG-01 BL-0013 / §Notes; no current plans for controlled measurement above 7 GHz. |
| B2 | QP-06 §6.2 GPSDO quarterly cross-check not actually independent | **Open** | Wording fix: specify a genuinely independent reference for the cross-check (a second GPSDO, a documented comparison to a national time service, or similar) or downgrade the claim. |
| B3 | QP-15 §4 missing clause 8.3.3(d) consequences-of-failure as a design input | **Done** | Added as input category 8 (2026-06-03 sweep). |
| B4 | QP-15 §6 / §2 8.3.4(a) results-to-be-achieved and 8.3.4(e) actions-on-problems not explicitly mapped | **Done** | Added to §2 mapping table and §6.4 (with §6.4 renumbered to §6.5) (2026-06-03 sweep). |
| B5 | QP-16 §4/§8 supplier approval recording is TODO | **Partial** | Five standing distributors named (RS, Mouser, Digi-Key, Farnell, Accu with cert). The InvenTree mechanism (company flag, group, supplier-note attachment) for marking "approved" still to be confirmed and documented. |
| B6 | QP-13 §5 phantom "nonconformity log (to be issued)" | **Done** | Routed to REG-03 as the combined nonconformity and corrective-action register (2026-06-03 sweep). |

## Group C — quality objectives unmeasurable

| # | Finding | Status | Note |
|---|---|---|---|
| C1 | QM-01 §6 obj 2 100% from go-live but no Part Test Templates / no serial scheme | **In flight** | Serial scheme defined (YYYYWWNN); Part Test Templates land during the Aalto build. Objective wording also worth softening to "from first production build under QP-11". |
| C2 | Obj 4 milestone notification record undefined | **Open** | Define the artefact in QP-04 / QP-15: the at-risk warning email retained under `06-handover/` is the record. Wording fix to make this explicit in the objective. |
| C3 | Obj 5 customer satisfaction no records | **In flight** | Aalto post-delivery debrief will produce the first record. Wording could also be reframed as a first-cycle baseline. |
| C4 | §6 closing para lumps obj 2 with obj 1 as directly-controlled | **Open** | Reword: obj 2 depends on supplier supply (batch goods-in) and is not wholly within direct control. |
| C5 | Obj 3 "logged within 5 working days" target not in QP-14 | **Open** | Add the 5-working-day logging target to QP-14 §4 / §6 so procedure and objective agree. |

## Group D — cross-cutting

| # | Finding | Status | Note |
|---|---|---|---|
| D1 | QP-07 §7 cites "QP-16 Supplier and Associate Control" — wrong title | **Done** | Corrected to "QP-16 Purchasing and Supplier Control" (2026-06-03 sweep). |
| D2 | "MTI Technology" appears only in QP-17, contradicts REG-02 R-07 / QM-02 §4 client-concentration analysis | **Done** | Confirmed real (RF feasibility study, mti-technology.com); added to REG-02 R-07 client-concentration narrative and QM-02 §4 Clients row (2026-06-03 sweep). |

## Minor wording, consistency and cross-reference fixes

| Finding | Status | Note |
|---|---|---|
| QM-01 §10 escrow generic vs techUK named elsewhere | **Done** | QM-01 §10 and REG-02 R-01 / O-02 now name techUK Escrow consistently (2026-06-03 sweep). |
| QM-01 §1 / §10 Cyber Essentials currency claim | **Done** | Cert filed; current to 2027-05-22 (`qms/records/cyber-essentials/`). |
| QP-08 §7 cites QP-15 as colloquial "(prove stage)" not its title | **Done** | Now reads "QP-15 Design and Development" (2026-06-03 sweep). |
| QP-08 §1 / §2 Terms of Business title varies | Open | Confirm canonical wording ("Terms of Business v2.1 (Design Services)") and standardise. |
| QP-17 §3 vs §4 — "if a scale is adopted" contradicts mandatory 1–5 ratings | **Done** | QP-17 §4 now records the 1–5 ratings on Q2–Q5 as standard (2026-06-03 sweep). |
| QP-03 §3 Client Liaison row — clause-mapping slip | **Done** | Reordered to "customer satisfaction (QP-17, clause 9.1.2); control of customer property (QP-12, clause 8.5.3)" (2026-06-03 sweep). |
| QP-15 §6.3 broken refs | **Done** | §7 → §6.3 (line 53) and §4.3 → §4 item 3 fixed (2026-06-03 sweep). |
| QP-06 §3 cross-ref "(§6, §10)" — wrong target | **Done** | §10 reference removed (2026-06-03 sweep). |
| QP-06 §6 item 1 "triggers §8" — should be §7 | **Done** | Corrected to §7 (2026-06-03 sweep). |
| QP-11 §5 "Salable and built" — wrong trigger | **Done** | Replaced with "marked trackable and produced via an in-house build order"; QM-01 obj 2 aligned (2026-06-03 sweep). |
| QP-11 §5.1 "build completion is gated" stated as live | **Done** | Qualified "where Part Test Templates have been configured for a product, build completion is gated…" (2026-06-03 sweep). |
| QP-11 §5.1 instrument asset tag "in result notes or attached file" — ambiguous | Open | Pick one primary location (result notes), file as corroboration. |
| QP-11 §4.2 / QP-13 §3 / QP-16 §7 — three different phrasings for InvenTree quarantine/rejected status | Open | Standardise on one named InvenTree status string. |
| QP-16 §7 has its own disposition list duplicating QP-13 §4 | Open | Replace with pointer to QP-13 §4. |
| QP-16 §7 / QP-11 §5.2 batch acceptance criteria not defined | **Done** | PTP-02 (Paradar 5 dBi whip) defines the criteria via ISO 2859-1 attribute sampling (AQL 2.5%, Level II, lot=50, n=8, Ac=0) with switching rules; acceptance recorded in REG-06. QP-16 §7 and QP-11 §5.2 updated to reference it (2026-06-04). |
| QP-15 §7.1 serialised handover content stated as standard for every engagement | Open | Make conditional ("where the engagement delivers manufactured units…"). |
| QP-15 §3.4 per-engagement competence-coverage confirmation produces no record | Open | State the confirmation is captured in the scope record. |
| QP-06 §6 residual-directivity / match check from planning notes dropped on promotion | Open | Restore the post-cal in-use confidence check. |
| QP-10 §3 OWL framed as both Paradar own-brand product and Noktura client work | **Done** | Disambiguated: Paradar OWL driver boards as own-brand product line; Noktura OWL v3.0 redesign as public client engagement (2026-06-03 sweep). |
| QP-09 §4.5 follow-up "by Patrick where agreed" — independence question | Open | Tighten or remove the Patrick-led close-out path; follow-up by the external auditor at the next audit. |
| QP-07 §3 inputs omit explicit REG-02 / REG-03 references | Open | Add for two-way trace. |
| QP-07 §5 management-review minute template (QF-02) still TODO | Open | Issue alongside QF-01 when the first review approaches. |
| REG-01 INS-08 horn antenna basis under "maintained" with unknown basis | **Done** | BL-0045 Tekbox TBMA4 batch test report filed; basis recorded. |
| REG-01 INS-04 GPSDO output frequency / distribution path | **Done** (asset tag) / Open (distribution path) | Asset tag BL-0047 added. Distribution path (which instruments are switched to external reference) still to record per-measurement, per QP-06 §5. |
| REG-01 clause_refs missing 7.1.5.1 | **Done** | Added at REG-01 v1.1. |
| REG-02 R-08 rated Medium under its own "halts measurement capability" test | Open | Reconsider: arguably High given uninsured total-loss exposure (cyber-event BI cover only). Will be reconsidered once Hiscox extension is in place. |

## Cross-cutting consistency pass (from agent 9)

| Finding | Status | Note |
|---|---|---|
| Frontmatter complete and uniform across all documents | **Done** | Confirmed at review. |
| Numbering scheme followed | **Done** | Confirmed. |
| "load-bearing" not present in `/qms/` | **Done** | Confirmed. |
| Confidentiality posture (Aalto HAPS / Airbus) consistent across docs | **Done** | Harmonised in earlier sweep. |
| Built-vs-imported InvenTree model consistent | **Done** | Harmonised. |
| Clause 4–10 coverage complete | **Done** | Confirmed at review. |
